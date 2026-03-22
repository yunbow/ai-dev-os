# Lifespan Layers — The 4-Layer Model for AI Coding Rules

## Overview

AI Dev OS organizes developer knowledge into four layers, each with a distinct lifespan and abstraction level.

```text
┌──────────────────────────────────────────────────────┐
│ L1: Philosophy                    Lifespan: 2-5 years │
│ "Why we build this way"                               │
│ Core values that transcend tools and languages         │
├──────────────────────────────────────────────────────┤
│ L2: Decision Criteria             Lifespan: 1-3 years │
│ "How to decide"                                       │
│ Design and architecture principles                     │
├──────────────────────────────────────────────────────┤
│ L3: Guidelines                    Lifespan: 6-12 months│
│ "What to do"                                          │
│ Concrete, verifiable coding rules                      │
├──────────────────────────────────────────────────────┤
│ L4: AI Frames                     Lifespan: 2-4 months │
│ "How to communicate"                                  │
│ Tool-specific configurations and workflows             │
└──────────────────────────────────────────────────────┘
```

## Design Principles

### Dependency Rule (from Clean Architecture)

Upper layers MUST NOT reference lower layers.

- L1 must not contain tool names ("Claude Code", "Cursor") or framework names ("Next.js", "FastAPI")
- L2 must not contain framework-specific implementation details
- L3 may reference frameworks but not specific tool configurations
- L4 is tool-specific by definition

### Lifespan = Abstraction Level

The more abstract a layer, the longer it lives. This is not coincidental — it is a universal law observed across 15 classical software engineering theories (see [classical-theories.md](../theory/classical-theories.md)).

### Each Layer is Qualitatively Different

Layers are not levels of detail. They serve different purposes for different audiences (per Zachman Framework):

| Layer | Purpose | Audience | AI compliance |
|-------|---------|----------|:---:|
| L1 | Align team values | Everyone | Not measurable — abstract principles |
| L2 | Guide architectural decisions | Architects, senior engineers | Partially — provides reasoning context |
| L3 | Enforce coding standards | All developers | **Measurable and enforceable** |
| L4 | Configure AI tools | AI tool users | Directly executable |

### L1/L2 Are for Humans, L3/L4 Are for AI

[Benchmark data](https://github.com/yunbow/ai-dev-os-benchmark) reveals an important distinction:

- **L3 (Guidelines)** are directly enforceable by AI. Rules like "MUST use `.refine()` for date validation" produce measurable compliance changes (0% → 100%).
- **L1 (Philosophy)** and **L2 (Decision Criteria)** are abstract by design. "Correctness over convenience" or "prefer explicit error types" cannot be mechanically verified. Their value is in **aligning human team members on shared judgment criteria**, not in AI compliance.

This means:

- L1/L2 should be written for **humans to read and internalize**, not optimized for AI context injection
- L3/L4 should be written with **maximum specificity** — naming exact methods, patterns, and anti-patterns
- CLAUDE.md should primarily contain L3 rules; L1/L2 are better suited for team onboarding and code review discussions

## Specificity Cascade

When rules conflict, resolve by specificity — inspired by CSS:

```text
1. [Highest] frameworks/[stack]/*   ← Most specific
2. [High]    common/*               ← Common but concrete
3. [Medium]  project-specific/*     ← Project context
4. [Low]     02_decision-criteria/* ← Abstract criteria
5. [Lowest]  01_philosophy/*        ← Most abstract
```

## Rule Harvesting

Rules are discovered bottom-up, not written top-down:

1. **Code** — Let AI generate code
2. **Review** — Find gaps between output and expectations
3. **Harvest** — Extract gaps into explicit guidelines (L3)
4. **Discover** — Find patterns across rules (L2 → L1)

This approach ensures rules are grounded in real experience, not hypothetical ideals.

## Tool Independence

The 4-layer model separates concerns by lifespan:

- **L1–L3 (75%)** — Tool-independent. Survives migration between Claude Code, Kiro, Cursor, etc.
- **L4 (25%)** — Tool-specific. Implemented by each plugin repository.

This is the key differentiator of AI Dev OS: when you switch AI tools, 75% of your investment is preserved.

## Two-Tier Context Strategy

Not all guidelines should be loaded into the AI's context at all times. [Benchmark data](https://github.com/yunbow/ai-dev-os-benchmark) shows that loading too many guidelines **degrades** AI output quality through attention dilution — loading all 28 guideline files scored lower than no guidelines at all.

**Static context** (CLAUDE.md / .cursorrules / AGENTS.md):

- Loaded by the AI in every conversation
- Should contain only **3-5 project-specific guideline files** (~8K tokens) — patterns the AI cannot infer from its training data (e.g., project directory conventions, specific validation patterns, security requirements unique to your stack)
- Do NOT include general best practices (error handling, naming, API design) — the AI already knows these from training
- Curate manually — do not auto-remove based on violation frequency

**Dynamic checks** (plugin skills/rules):

- Invoked on demand (`/ai-dev-os-check`) or automatically via hooks
- Verify against a **specific checklist** of concrete, actionable items — not the full guideline text
- The AI reviews its own generated code and **fixes violations** in a focused review task
- This is the **primary quality mechanism** — benchmark data shows dynamic check+fix produces +9.9 points improvement vs baseline, while static guidelines alone show near-zero improvement

**The generate → check → fix loop:**

```text
CLAUDE.md (3-5 files, ~8K tokens)  → AI generates code
                                        ↓
/ai-dev-os-check (checklist, ~3K)  → AI reviews and fixes violations
                                        ↓
                                    Final output (benchmark: 96.9/100)
```

### Why Static Guidelines Are a Zero-Sum Game

[Benchmark data](https://github.com/yunbow/ai-dev-os-benchmark) reveals that static guidelines (CLAUDE.md) **redistribute** the AI's attention but do not increase its total quality budget:

- Items covered by guidelines improve (e.g., IDOR prevention: 0% → 100%)
- Items NOT covered by guidelines may regress (e.g., error boundary placement drops when security rules dominate context)
- The overall score remains approximately the same (guideline condition ≈ baseline across 10+ tests)

This is caused by **attention dilution** — a known property of transformer-based LLMs. As context length increases, each individual rule receives proportionally less attention from the self-attention mechanism. At ~75K tokens (all 28 guidelines), the AI performs worse than with no guidelines at all.

The solution is not "better guidelines" but **fewer guidelines + post-generation verification**:

- Static context: only what the AI cannot infer from training data (~8K tokens)
- Dynamic check: comprehensive verification after generation, where attention is fully focused on review

This two-tier approach solves both problems:

- "Too many rules degrade quality" → static context is minimal and project-specific
- "Important rules must not be missed" → dynamic check+fix catches everything post-generation

## The Sentinel Rule

> **Absence of violations proves presence of protection, not absence of need.**

A security rule with zero violations is *working*. Removing it because it "never fires" would immediately cause regressions. This principle applies to all high-stakes rules (security, auth, data integrity):

- Never auto-remove rules based on low violation frequency
- Never deprioritize rules that have prevented issues
- When curating static context, always keep security and auth rules regardless of violation count

---

Languages: English | [日本語](../docs/i18n/ja/spec/4-layer-model.md) | [简体中文](../docs/i18n/zh-CN/spec/4-layer-model.md) | [한국어](../docs/i18n/ko/spec/4-layer-model.md) | [Español](../docs/i18n/es/spec/4-layer-model.md)

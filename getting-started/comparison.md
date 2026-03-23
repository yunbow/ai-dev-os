# AI Dev OS in 5 Minutes — Framework Comparison

## What is AI Dev OS? — AI Coding Rules Framework

A framework for turning tacit developer knowledge into explicit, enforceable rules for AI-assisted coding. Unlike workflow orchestration tools, AI Dev OS treats the problem as **knowledge management**.

## Quick Comparison

| | AI Dev OS | ContextKit (Anthropic) | Spec Kit (GitHub) | GSD | BMAD | bkit |
|---|---|---|---|---|---|---|
| **Core idea** | Knowledge layers with lifespans | Structured context documents | Spec as source of truth | Execution orchestration | Multi-agent roles | PDCA cycles |
| **Rule organization** | 4 layers (Philosophy → Decision Criteria → Guidelines → AI Frames) | Product/Architecture/Style docs | Flat spec/plan/task | 3 documents | 19 agents, 50+ workflows | Phase-based |
| **Tool support** | Claude Code + Kiro + Cursor | Claude Code (primary) | Cross-tool (shell) | Claude Code only | Multi-tool | Gemini + Claude |
| **Rule evolution** | Built-in (`ai-dev-os-evolve`) | Manual | Manual | Manual | Manual | Manual |
| **Conflict resolution** | Specificity Cascade | Not defined | Not defined | Not defined | Not defined | Not defined |
| **Context overload** | Two-tier (static 3-5 rules + dynamic full check) | Document-level scoping | Not addressed | Fresh sub-agent | Agent specialization | Hook-based |
| **Tool migration** | 75% preserved (L1-L3 portable) | Partially portable | Spec survives | State docs survive | Docs survive | Session-based |
| **Theoretical basis** | 16 classical SE theories | Context engineering | SDD methodology | Context engineering | Agile + agents | PDCA |
| **Setup** | `npx ai-dev-os init` (CLI) | Manual Markdown creation | Shell scripts | Prompt-based | Multi-step wizard | Config files |

## When to Choose AI Dev OS

**Choose AI Dev OS if you:**

- Want rules that survive tool changes (Claude Code → Kiro → Cursor)
- Need a system that improves over time (Rule Harvesting + SECI spiral)
- Value "why" over "what" — understanding principles, not just following templates
- Work across multiple projects and want reusable guidelines

**Choose something else if you:**

- Want lightweight context documents without a layered model (→ ContextKit)
- Want a one-session workflow optimizer (→ GSD)
- Need multi-agent orchestration for large teams (→ BMAD)
- Want GitHub-native spec management (→ Spec Kit)

## Trade-offs

AI Dev OS is not the right choice for every situation:

- **Upfront investment**: You won't see value in the first 30 minutes. Rules need to be written and refined over time.
- **Setup complexity**: Even with the CLI, the submodule model requires git knowledge. Non-git workflows are not supported.
- **Rule maintenance**: Rules need periodic review. Without discipline, they become stale.

## Key Differentiators

### 1. Rules with Expiration Dates

Every rule has a shelf life. L1 (philosophy) lasts 2-5 years. L4 (tool config) lasts 2-4 months. This prevents rule rot.

### 2. Bottom-Up Rule Discovery

Don't write rules top-down. Let AI generate code, find gaps, extract rules from real failures. Rules grounded in experience, not theory.

### 3. "Less is More" for Context

[Benchmark data](https://github.com/yunbow/ai-dev-os-benchmark) proves too many rules degrade AI output. AI Dev OS loads only 3-5 project-specific files in static context (~8K tokens), then verifies all rules post-generation via dynamic check+fix. This scored 96.9/100 vs 79.3/100 for loading all guidelines.

### 4. The Sentinel Rule

Security rules with zero violations are *working* — never remove them for being "unused."

### 5. AI Cost Optimization

AI Dev OS reduces AI-related costs in three ways:

- **Fewer rework cycles**: Specific guidelines + post-generation check catches issues before code review, reducing human review time
- **Token efficiency**: 3-5 files (~8K tokens) in static context instead of 28 files (~75K tokens) — 90% token reduction with better results
- **Tool migration savings**: 75% of rules survive tool changes (L1-L3). Switching from Claude Code to Cursor doesn't mean rewriting all your coding standards

## Design Philosophy: Markdown by Design

AI Dev OS is intentionally composed entirely of Markdown files. This is a deliberate design decision, not a limitation:

- **Transparency**: Every rule is human-readable. No compilation, no binary formats, no opaque configurations.
- **Forkability**: Anyone can fork, modify, and redistribute rules without learning a proprietary tool or DSL.
- **Tool independence**: Markdown works with any editor, any AI tool, any CI system. No vendor lock-in.

The [CLI tool](https://github.com/yunbow/ai-dev-os-cli) (`npx ai-dev-os init`) automates setup, but the underlying model is still git submodules — rules live in your repository as auditable, diffable text files. The CLI is optional; manual setup is always supported.

---

Languages: English | [日本語](../docs/i18n/ja/getting-started/comparison.md) | [简体中文](../docs/i18n/zh-CN/getting-started/comparison.md) | [한국어](../docs/i18n/ko/getting-started/comparison.md) | [Español](../docs/i18n/es/getting-started/comparison.md)

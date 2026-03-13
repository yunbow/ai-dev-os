# AI Code Review: Guidelines vs Multi-Agent Review — When to Use Which

## The Question

> "Should I use AI Dev OS guidelines, or have multiple LLMs debate my code?"

**Answer: Both — but at different layers.**

AI Dev OS guidelines and multi-LLM review are not alternatives. They cover different quality dimensions and work best when combined based on risk level.

## The Core Insight

```
Quality
 ↑
 |          ┌─── Multi-LLM debate (ceiling effect)
 |         ╱     Discovers unknown issues: edge cases, zero-days, design trade-offs
 |        ╱
 |       ╱
 |  ════╪══════ Guidelines (floor effect)
 |      |       Guarantees baseline: naming, patterns, security checklist, consistency
 |      |
 └──────┴──────→ Cost
```

- **Guidelines raise the floor** — reproducible, near-zero cost, knowledge accumulates over time
- **Multi-LLM debate raises the ceiling** — explores unknown problems, but expensive and non-reproducible

## Quality Dimensions

| Quality Dimension | Guidelines (AI Dev OS) | Multi-LLM Debate | Primary Owner |
|---|---|---|---|
| Conformance (coding standards) | ★★★★★ | ★★ | Guidelines |
| Maintainability (naming, structure) | ★★★★★ | ★★ | Guidelines |
| Correctness (logic bugs) | ★★★ | ★★★★ | Multi-LLM |
| Robustness (edge cases) | ★★ | ★★★★ | Multi-LLM |
| Security (vulnerabilities) | ★★★ | ★★★★★ | Multi-LLM (+ Guidelines) |
| Knowledge retention | ★★★★★ | ★ | Guidelines |
| Cost efficiency | ★★★★★ | ★★ | Guidelines |

## Task-Based Guide

| Task | Risk | Recommended Approach | Est. Cost |
|---|---|---|---|
| CRUD implementation | Low | Guidelines only (`/ai-dev-os-check`) | ~$0 |
| UI components | Low | Guidelines only | ~$0 |
| Business logic | Medium | Guidelines + single-LLM review (separate session) | ~$0.04 |
| Refactoring | Medium | Guidelines + test suite | ~$0 |
| API design | Medium-High | Guidelines + 2-model review | ~$0.40 |
| Security-related code | High | Guidelines + 3-model debate | ~$0.80 |
| Payment / authentication | Critical | Guidelines + 3-model debate + human review | ~$0.80+ |
| Architecture decisions | High | 3-model debate (no single right answer) | ~$0.80 |

## The Recommended Model: Guideline-First, Debate-on-Risk

```
Phase 1: Code Generation
  AI writes code with AI Dev OS guidelines loaded in context (CLAUDE.md)
  → Baseline quality via static rules (10-15 high-impact rules)
  → Cost: included in normal AI coding

Phase 2: Pre-Commit Check (/ai-dev-os-check)
  Comprehensive check against 30+ rules
  → Catches conformance and known pattern violations
  → Cost: near-zero

Phase 3: PR Review (risk-based)
  Auto-detect: changes to security/payment/auth files
  → High-risk PRs only: trigger cross-model review
  → Cost: only for 10-20% of PRs

Phase 4: Knowledge Feedback
  New patterns discovered by multi-LLM debate → add to L3 guidelines
  → Next time, the same issue is caught at near-zero cost
  → This is Rule Harvesting in action
```

## Why Not Just Multi-LLM Debate for Everything?

| Concern | Data |
|---|---|
| **Cost** | Multi-agent systems consume 4-220x more tokens than single-agent (ICLR 2025). For a team of 10 developers, all-PR debate = ~$16,000/month vs guidelines at ~$0 |
| **Reproducibility** | Same code + same models = different results each time. Guidelines produce deterministic checks |
| **Knowledge loss** | Debate results are volatile — last week's insights don't carry to next review. Guidelines accumulate |
| **Adoption barrier** | Less than 10% of enterprises successfully scale multi-agent systems. `npx ai-dev-os init` works on day one |
| **False positives** | LLMs systematically over-correct correct code and misattribute defect causes (2026 research) |

## Why Not Just Guidelines?

| Concern | Data |
|---|---|
| **Sycophancy** | LLMs agree with user expectations 56-62% of the time (SycEval, AAAI 2025). Even when checking guidelines, the reviewing LLM may apply rules leniently — ~40% residual sycophancy risk |
| **Static blind spots** | Guidelines only catch what's been written down. Novel vulnerabilities, unexpected edge cases, and domain-specific issues require exploration |
| **Same-model bias** | A single model has one set of biases. It systematically misses the same types of bugs every time |

## The Feedback Loop

The most powerful insight: **multi-LLM debate is a guideline discovery engine**.

```
Multi-LLM debate finds new pattern
  → Extract as L3 guideline (Rule Harvesting)
  → Add to ai-dev-os rules
  → Next time: caught by /ai-dev-os-check at zero cost
  → Debate budget freed for the next unknown
```

Over time, the guideline set grows to cover more patterns, and the debate budget is concentrated on genuinely novel issues. This creates a virtuous cycle.

## Related

- [Framework Comparison](./comparison.md) — AI Dev OS vs Spec Kit, GSD, BMAD, ContextKit
- [Quick Start](./quick-start.md) — Get started with AI Dev OS
- [AI Dev OS CLI](https://github.com/yunbow/ai-dev-os-cli) — Setup in one command

---

Languages: English | [日本語](../docs/i18n/ja/getting-started/guideline-vs-multi-agent.md) | [简体中文](../docs/i18n/zh-CN/getting-started/guideline-vs-multi-agent.md) | [한국어](../docs/i18n/ko/getting-started/guideline-vs-multi-agent.md) | [Español](../docs/i18n/es/getting-started/guideline-vs-multi-agent.md)

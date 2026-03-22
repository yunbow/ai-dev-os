# AI Dev OS

[![Lint & Link Check](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml/badge.svg)](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

> Turn tacit developer knowledge into explicit, enforceable rules for AI-assisted coding.

Coding rules framework for AI assistants — Claude Code, Cursor, and Kiro

```
> /ai-dev-os-check

## AI Dev OS Check & Fix Report
- Files checked: 12
- ✅ Passed: 45 / 🔧 Fixed: 3 / ⚠️ Manual Review: 1

| # | File              | Rule         | What was fixed              |
|---|-------------------|--------------|-----------------------------|
| 1 | route.ts:42       | security.md  | Added rate limiting         |
| 2 | user-card.tsx:7   | naming.md    | Renamed to kebab-case       |
| 3 | action.ts:15      | validation.md| Added .refine() for dueDate |
```

## Why AI Dev OS?

Your AI writes code that looks right — but violates team conventions.
Your coding standards live in senior developers' heads, not in AI context.

AI Dev OS solves this by making tacit knowledge explicit:

- **75% survives tool migrations** — Rules are tool-independent (L1–L3). Switch Claude Code → Kiro → Cursor freely
- **Rules improve over time** — Harvest rules from real code reviews, not hypothetical ideals (Rule Harvesting)
- **Near-zero cost** — 3-5 static rules in context + comprehensive dynamic check & fix on demand ([benchmark: 96.9/100](https://github.com/yunbow/ai-dev-os-benchmark))
- **Pure Markdown** — No DSL, no compilation. Fork, modify, and audit every rule

AI Dev OS complements your AI tool — it doesn't replace it. Claude Code, Kiro, and Cursor handle code generation; AI Dev OS handles the rules they follow.

![AI Dev OS Check & Fix Report](docs/images/ai-dev-os-check.png)

## Quick Start

```bash
npx ai-dev-os init
```

Pick a language (`typescript` / `python`) and a tool (`claude-code` / `kiro` / `cursor`).

```bash
# Non-interactive:
npx ai-dev-os init --rules typescript --plugin claude-code
```

> [CLI details](https://github.com/yunbow/ai-dev-os-cli) | [Manual setup](getting-started/quick-start.md) | [Choose Rules](getting-started/choose-rules.md) | [Choose Plugin](getting-started/choose-plugin.md)

## Lifespan Layers — The 4-Layer Model

| Layer | Name | Lifespan | Purpose |
|-------|------|----------|---------|
| L1 | Philosophy | 2-5 years | Core values that transcend tools and languages |
| L2 | Decision Criteria | 1-3 years | Design and architecture decision criteria |
| L3 | Guidelines | 6-12 months | Concrete, verifiable coding rules |
| L4 | AI Frames | 2-4 months | Tool-specific configurations and workflows |

Upper layers are abstract and stable; lower layers are concrete and volatile.
When you switch tools, L1–L3 (75%) stay intact — only L4 changes.

## Key Concepts

**Specificity Cascade** (rule conflict resolution) — When rules conflict, the most specific wins (like CSS specificity). Framework rules > common rules > project conventions > principles > philosophy. [→ Details](spec/priority-cascade.md)

**Rule Harvesting** (bottom-up rule discovery) — Don't write rules top-down. Let AI code → review gaps → harvest into rules. Grounded in real experience. [→ Details](spec/4-layer-model.md#rule-harvesting)

**Guideline Capital** (guidelines as intellectual assets) — Guidelines are intellectual capital, not disposable prompts. Unlike Technical Debt (liability), Guideline Capital is an asset that compounds. [→ Details](getting-started/comparison.md)

**Two-Tier Context Strategy** (generate + verify + fix) — Load only 3-5 project-specific files in CLAUDE.md (~8K tokens). Verify all rules post-generation via `/ai-dev-os-check`. [Benchmark data](https://github.com/yunbow/ai-dev-os-benchmark) shows this approach scores 96.9/100, while loading 10+ files scores lower than no guidelines at all. [→ Details](spec/4-layer-model.md#two-tier-context-strategy)

## Works With

AI Dev OS provides a structured approach to writing effective AI coding rule files:

- **Claude Code** — via `CLAUDE.md` and custom skills ([plugin](https://github.com/yunbow/ai-dev-os-plugin-claude-code))
- **Kiro** — via `AGENTS.md` and steering rules ([plugin](https://github.com/yunbow/ai-dev-os-plugin-kiro))
- **Cursor** — via `.cursorrules` and `.mdc` files ([plugin](https://github.com/yunbow/ai-dev-os-plugin-cursor))

## Ecosystem

| Repository | Description |
|---|---|
| **ai-dev-os** (this repo) | Framework specification and theory |
| [rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript / Next.js / Node.js guidelines |
| [rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python / FastAPI guidelines |
| [plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Skills, Hooks, and Agents for Claude Code |
| [plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Steering Rules and Hooks for Kiro |
| [plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Cursor Rules (.mdc) |
| [cli](https://github.com/yunbow/ai-dev-os-cli) | `npx ai-dev-os init` |
| [benchmark](https://github.com/yunbow/ai-dev-os-benchmark) | Quantitative benchmark — guideline impact data |

## Learn More

- [4-Layer Model](spec/4-layer-model.md) | [Dependency Rule](spec/dependency-rule.md) | [Specificity Cascade](spec/priority-cascade.md) | [Shelf-Life Model](spec/shelf-life.md)
- [Tacit-to-Explicit Engineering](theory/tacit-to-explicit.md) | [Classical Theories](theory/classical-theories.md) | [Future-Proofing](theory/future-proofing.md)
- [Framework Comparison](getting-started/comparison.md) | [Guidelines vs Multi-Agent](getting-started/guideline-vs-multi-agent.md) | [Tool Migration](getting-started/migration.md)
- [Zenn Book: AI DEV OS (Japanese)](https://zenn.dev/yun_bow)

<details>
<summary>Directory Structure</summary>

```
ai-dev-os/
├── spec/                        # Framework Specification
│   ├── 4-layer-model.md         #   Lifespan Layers (4-layer model)
│   ├── dependency-rule.md       #   Dependency rule
│   ├── priority-cascade.md      #   Specificity Cascade
│   ├── shelf-life.md            #   Shelf-life model
│   └── governance.md            #   Governance model
├── theory/                      # Theoretical Background
├── getting-started/             # Getting Started Guide
└── docs/                        # Operation Guide & i18n
```

> The actual guideline files (01_philosophy/ ... 04_ai-prompts/) are in the
> [rules repositories](https://github.com/yunbow/ai-dev-os-rules-typescript), not in this core repo.

</details>

## License

[MIT](./LICENSE)

---

Languages: English | [日本語](docs/i18n/ja/README.md) | [简体中文](docs/i18n/zh-CN/README.md) | [한국어](docs/i18n/ko/README.md) | [Español](docs/i18n/es/README.md)

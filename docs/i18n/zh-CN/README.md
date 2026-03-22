# AI Dev OS

[![Lint & Link Check](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml/badge.svg)](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../../../LICENSE)

> 将开发者的隐性知识转化为 AI 辅助编程的显性可执行规则。

AI 助手的编程规则框架 — 支持 Claude Code、Cursor 和 Kiro

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

## 为什么选择 AI Dev OS？

你的 AI 写出的代码看起来没问题——但违反了团队规范。
编码标准存在于资深开发者的脑中，而不在 AI 的上下文里。

AI Dev OS 通过将隐性知识显性化来解决这个问题：

- **75% 经受住工具迁移** — 规则与工具无关（L1–L3）。Claude Code → Kiro → Cursor 自由切换
- **规则持续改进** — 从真实代码审查中收获规则，而非假设的理想（Rule Harvesting）
- **几乎零成本** — 上下文中 3-5 条静态规则 + 按需全面检查和修复（[基准测试: 96.9/100](https://github.com/yunbow/ai-dev-os-benchmark)）
- **纯 Markdown** — 无 DSL，无编译。Fork、修改、审计每一条规则

AI Dev OS 是 AI 工具的补充，而非替代。Claude Code、Kiro 和 Cursor 负责代码生成；AI Dev OS 负责它们遵循的规则。

![AI Dev OS Check & Fix Report](../../../docs/images/ai-dev-os-check.png)

## 快速开始

```bash
npx ai-dev-os init
```

选择语言（`typescript` / `python`）和工具（`claude-code` / `kiro` / `cursor`）。

```bash
# 非交互模式：
npx ai-dev-os init --rules typescript --plugin claude-code
```

> [CLI 详情](https://github.com/yunbow/ai-dev-os-cli) | [手动设置](getting-started/quick-start.md) | [选择规则](getting-started/choose-rules.md) | [选择插件](getting-started/choose-plugin.md)

## Lifespan Layers — 4 层模型

| 层 | 名称 | 生命周期 | 用途 |
|-------|------|----------|---------|
| L1 | 哲学 | 2-5 年 | 超越工具和语言的核心价值观 |
| L2 | 判断标准 | 1-3 年 | 设计和架构决策标准 |
| L3 | 指南 | 6-12 个月 | 具体的、可验证的编码规则 |
| L4 | AI 框架 | 2-4 个月 | 工具特定的配置和工作流 |

上层抽象且稳定；下层具体且易变。
切换工具时，L1–L3（75%）保持不变——只有 L4 需要改变。

## 核心概念

**Specificity Cascade (rule conflict resolution)** — 当规则冲突时，最具体的规则优先（类似 CSS 特异性）。框架规则 > 通用规则 > 项目约定 > 原则 > 哲学。[→ 详情](spec/priority-cascade.md)

**Rule Harvesting** (bottom-up rule discovery) — 不要自上而下编写规则。让 AI 写代码 → 审查发现差距 → 收获为规则。自下而上，基于真实经验。[→ 详情](spec/4-layer-model.md#rule-harvesting)

**Guideline Capital** (guidelines as intellectual assets) — 指南不是一次性提示词，而是知识资本。与 Technical Debt（负债）不同，Guideline Capital 是不断增值的资产。[→ 详情](getting-started/comparison.md)

**Two-Tier Context Strategy** (generate + verify + fix) — CLAUDE.md 中仅加载 3-5 个项目特定文件（~8K tokens）。所有规则通过 `/ai-dev-os-check` 进行事后验证。[基准测试数据](https://github.com/yunbow/ai-dev-os-benchmark)显示此方法得分 96.9/100，而加载 10+ 文件的得分低于无指南基线。

## 支持的工具

AI Dev OS 提供了一种结构化方法来编写有效的 AI 编程规则文件：

- **Claude Code** — 通过 `CLAUDE.md` 和自定义 Skills（[插件](https://github.com/yunbow/ai-dev-os-plugin-claude-code)）
- **Kiro** — 通过 `AGENTS.md` 和 Steering Rules（[插件](https://github.com/yunbow/ai-dev-os-plugin-kiro)）
- **Cursor** — 通过 `.cursorrules` 和 `.mdc` 文件（[插件](https://github.com/yunbow/ai-dev-os-plugin-cursor)）

## 生态系统

| 仓库 | 说明 |
|---|---|
| **ai-dev-os**（本仓库） | 框架规范和理论 |
| [rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript / Next.js / Node.js 指南 |
| [rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python / FastAPI 指南 |
| [plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Claude Code 的 Skills、Hooks 和 Agents |
| [plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Kiro 的 Steering Rules 和 Hooks |
| [plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Cursor Rules (.mdc) |
| [cli](https://github.com/yunbow/ai-dev-os-cli) | `npx ai-dev-os init` |
| [benchmark](https://github.com/yunbow/ai-dev-os-benchmark) | 定量基准测试 — 指南对 AI 代码质量的影响数据 |

## 了解更多

- [4 层模型](spec/4-layer-model.md) | [依赖规则](spec/dependency-rule.md) | [Specificity Cascade](spec/priority-cascade.md) | [保质期模型](spec/shelf-life.md)
- [Tacit-to-Explicit Engineering](theory/tacit-to-explicit.md) | [经典理论映射](theory/classical-theories.md) | [面向未来](theory/future-proofing.md)
- [框架比较](getting-started/comparison.md) | [指南 vs 多智能体](getting-started/guideline-vs-multi-agent.md) | [工具迁移指南](getting-started/migration.md)
- [Zenn Book: AI DEV OS (Japanese)](https://zenn.dev/yun_bow)

<details>
<summary>目录结构</summary>

```
ai-dev-os/
├── spec/                        # 框架规范
│   ├── 4-layer-model.md         #   Lifespan Layers（4 层模型）
│   ├── dependency-rule.md       #   依赖规则
│   ├── priority-cascade.md      #   Specificity Cascade
│   ├── shelf-life.md            #   保质期模型
│   └── governance.md            #   治理模型
├── theory/                      # 理论背景
├── getting-started/             # 入门指南
└── docs/                        # 运维指南 & 多语言
```

> 实际的指南文件（01_philosophy/ ... 04_ai-prompts/）位于
> [规则仓库](https://github.com/yunbow/ai-dev-os-rules-typescript)，不在本核心仓库中。

</details>

## 许可证

[MIT](../../../LICENSE)

---

Languages: [English](../../../README.md) | [日本語](../ja/README.md) | 简体中文 | [한국어](../ko/README.md) | [Español](../es/README.md)

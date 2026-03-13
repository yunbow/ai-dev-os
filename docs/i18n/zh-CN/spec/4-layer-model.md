# Lifespan Layers — AI 编程规则的4层模型

## 概述

AI Dev OS 将开发者知识组织为四个层，每层具有不同的生命周期和抽象级别。

```
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

## 设计原则

### 依赖规则（源自 Clean Architecture）

上层绝不能引用下层。

- L1 不得包含工具名称（"Claude Code"、"Cursor"）或框架名称（"Next.js"、"FastAPI"）
- L2 不得包含框架特定的实现细节
- L3 可以引用框架但不得包含特定的工具配置
- L4 按定义是工具特定的

### 生命周期 = 抽象级别

层越抽象，存续越久。这并非巧合 — 这是在 15 个经典软件工程理论中观察到的普遍规律（参见 [classical-theories.md](../theory/classical-theories.md)）。

### 各层质的不同

层不是详细程度的级别。根据 Zachman Framework，它们为不同受众服务于不同目的：

| 层 | 目的 | 受众 |
|-------|---------|----------|
| L1 | 统一团队价值观 | 所有人 |
| L2 | 指导架构决策 | 架构师、高级工程师 |
| L3 | 执行编码标准 | 所有开发者 |
| L4 | 配置 AI 工具 | AI 工具用户 |

## Specificity Cascade

当规则冲突时，按特异性解决：

```
1. [Highest] frameworks/[stack]/*   ← Most specific
2. [High]    common/*               ← Common but concrete
3. [Medium]  project-specific/*     ← Project context
4. [Low]     02_decision-criteria/* ← Abstract criteria
5. [Lowest]  01_philosophy/*        ← Most abstract
```

## Rule Harvesting

AI Dev OS 采用自下而上的方式构建，而非自上而下：

1. **先写代码** — 让 AI 生成代码
2. **审查** — 发现输出与预期之间的差距
3. **收获规则** — 将差距转化为显性指南（L3）
4. **发现原则** — 在规则间发现模式（L2）
5. **阐述哲学** — 定义核心价值观（L1）

这种方法确保规则基于实际经验，而非假设性的理想。

## 工具无关性

4 层模型按生命周期分离关注点：

- **L1-L3（75%）** — 工具无关。在 Claude Code、Kiro、Cursor 等工具之间迁移时保留。
- **L4（25%）** — 工具特定。由各插件仓库实现。

这是 AI Dev OS 的关键差异化因素：当您切换 AI 工具时，75% 的投资得以保留。

## Two-Tier Context Strategy（两层上下文策略）

不应始终将所有指南加载到 AI 的上下文中。研究表明规则过多会降低 AI 输出质量。

**静态上下文**（CLAUDE.md / .cursorrules / AGENTS.md）：
- AI 在每次对话中加载
- 应仅包含 **10-15 条高影响力指南**（安全、错误处理、命名、项目结构、框架概述）
- 手动精选 — 不基于违规频率自动删除（安全等低频规则可能正因其存在而发挥作用）

**动态检查**（插件 skills/rules）：
- 按需调用（`/ai-dev-os-check`、`/ai-dev-os-scan`、`/ai-dev-os-review`）
- 针对**所有指南**（30+）进行全面验证
- 不会分散注意力，因为 AI 在专注的审查任务中处理它们，而非在代码生成期间

这种两层方法同时解决了两个问题：
- "规则太多降低质量" → 静态上下文经过精选且聚焦
- "不能遗漏重要规则" → 动态检查覆盖所有内容

## 哨兵规则

> **违规的缺失证明了保护的存在，而非需求的缺失。**

零违规的安全规则是*有效的*。因为"从未触发"而删除它会立即导致回归。此原则适用于所有高风险规则（安全、认证、数据完整性）：

- 绝不基于低违规频率自动删除规则
- 绝不降低已防止问题的规则的优先级
- 精选静态上下文时，无论违规次数如何，始终保留安全和认证规则

---

Languages: [English](../../../../spec/4-layer-model.md) | [日本語](../../ja/spec/4-layer-model.md) | 简体中文 | [한국어](../../ko/spec/4-layer-model.md) | [Español](../../es/spec/4-layer-model.md)

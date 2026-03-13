# Specificity Cascade — AI Coding Rules

## CSS 特异性类比

AI Dev OS 使用受 CSS 特异性启发的优先级级联来解决规则冲突：

```
1. [Highest] frameworks/[stack]/*   ← Most specific
2. [High]    common/*               ← Common but concrete
3. [Medium]  project-specific/*     ← Project context
4. [Low]     02_decision-criteria/* ← Abstract criteria
5. [Lowest]  01_philosophy/*        ← Most abstract
```

> **注意**：`project-specific/*` 指的是用户项目中的指南（例如 `docs/guidelines/billing.md`），而非规则仓库中的内容。规则仓库仅包含 `frameworks/` 和 `common/`。项目特定指南由用户为领域逻辑、外部集成、法律要求等创建。

## 工作原理

1. 编码时，AI 首先查找**框架特定**规则（最具体）
2. 如果没有框架规则，回退到**通用**规则
3. 如果没有通用规则，回退到**项目特定**惯例
4. 如果没有显性规则，应用**判断标准**来推理最佳方法
5. 作为最后手段，回退到**哲学**进行基于价值观的判断

## 示例：错误处理

假设 AI 在 Next.js Server Action 中遇到错误处理决策：

1. **frameworks/nextjs/server-actions.md** 说"使用 ActionResult<T> 模式" → **应用此规则**
2. **common/error-handling.md** 说"将错误分为用户/系统/验证类型" → 同样适用
3. **02_decision-criteria/error-strategy.md** 说"优先使用显式错误类型而非异常" → 为方法提供参考
4. **01_philosophy/principles.md** 说"正确性优先于便利性" → 基础价值观

所有层都有贡献，但当存在冲突时，最具体的规则胜出。

---

Languages: [English](../../../../spec/priority-cascade.md) | [日本語](../../ja/spec/priority-cascade.md) | 简体中文 | [한국어](../../ko/spec/priority-cascade.md) | [Español](../../es/spec/priority-cascade.md)

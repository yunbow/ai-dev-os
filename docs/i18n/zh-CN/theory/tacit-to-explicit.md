# Tacit-to-Explicit Engineering（隐性知识→显性知识工程）

## 核心问题

> AI 生成的代码"看起来正确但有微妙的错误"——66% 的开发者将此视为最大的困扰。

根本原因不是提示不够充分或 AI 模型不好。而是**资深开发者的隐性知识尚未转化为显式的、可执行的规则**。

## 什么是隐性知识？

隐性知识（暗黙知）是难以表述的知识：

- "这段代码感觉不对" → 具体违反了什么规则？
- "我们这里不这样做" → "那样做"记录在哪里？
- "任何资深工程师都知道这个" → 但 AI 不是资深工程师

## SECI 模型的关联

AI Dev OS 直接映射到野中郁次郎的 SECI 知识创造模型（1995）：

| SECI 阶段 | AI Dev OS 层级 | 知识流动 |
|-----------|----------------|----------------|
| 社会化（共同化） | L1：哲学 | 隐性 → 隐性：通过经验共享 |
| 外化（表出化） | L2：决策标准 | 隐性 → 显性：以原则形式表述 |
| 组合化（連結化） | L3：指南 | 显性 → 显性：组织成规则 |
| 内化（内面化） | L4：AI 框架 | 显性 → 隐性：通过实践内化 |

关键洞察：**AI Dev OS 是一个知识创造系统，而不仅仅是文档层级结构。**

## 螺旋

SECI 模型是一个螺旋，而非单向过程：

```
L4 practice → discovers new tacit knowledge → L1 evolves
     ↑                                              ↓
     └──── L3 rules ← L2 principles ← L1 values ──┘
```

`/ai-dev-os-evolve` 命令通过分析近期编码实践并提出 L1-L2 的更新来实现这个螺旋。

## 为什么这很重要

没有显式规则：
- AI 生成的代码**看起来正确但违反了团队规范**
- 代码审查变成了对相同问题的**反复教学课程**
- 知识**随人员离开而流失**——AI 从未学到过

使用 AI Dev OS：
- 隐性知识被捕获为显式的、版本化的、可执行的规则
- AI **随着每次代码审查而改进**（通过Rule Harvesting）
- 知识**经受住团队变动**和工具迁移

## 参考文献

- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Nonaka, I. & Konno, N. (1998). "The Concept of 'Ba'." *California Management Review*, 40(3).

---

Languages: [English](../../../../theory/tacit-to-explicit.md) | [日本語](../../ja/theory/tacit-to-explicit.md) | 简体中文 | [한국어](../../ko/theory/tacit-to-explicit.md) | [Español](../../es/theory/tacit-to-explicit.md)

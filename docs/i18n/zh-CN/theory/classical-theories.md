# 经典软件工程理论

## 概述

AI Dev OS 的 4 层模型并非全新发明——它映射到跨越 50 年的 16 个已建立的软件工程理论中观察到的模式。

## 第一梯队：直接结构相似性

### Clean Architecture（Robert C. Martin，2012/2017）

| AI Dev OS | Clean Architecture | 稳定性 |
|-----------|-------------------|-----------|
| L1：哲学 | 实体（业务规则） | 最高 |
| L2：决策标准 | 用例（应用规则） | 高 |
| L3：指南 | 接口适配器 | 中 |
| L4：AI 框架 | 框架与驱动程序 | 最低 |

**关键洞察**：依赖规则——源代码依赖必须指向内部。

### Pattern Languages（Christopher Alexander，1977）

| AI Dev OS | Pattern Language | 尺度 |
|-----------|----------------|-------|
| L1：哲学 | "无名之质" | 城市 |
| L2：决策标准 | 大尺度模式 | 区域 |
| L3：指南 | 中尺度模式 | 建筑 |
| L4：AI 框架 | 小尺度模式 | 材料 |

**关键洞察**：较大的模式更长寿。抽象模式生成具体模式。

### SECI 模型（Nonaka & Takeuchi，1995）

| AI Dev OS | SECI | 知识流动 |
|-----------|------|----------------|
| L1：哲学 | 社会化 | 隐性 → 隐性 |
| L2：决策标准 | 外化 | 隐性 → 显性 |
| L3：指南 | 组合化 | 显性 → 显性 |
| L4：AI 框架 | 内化 | 显性 → 隐性 |

**关键洞察**：知识创造是螺旋式的，而非线性的。实践反馈到哲学。

### 敏捷宣言（2001）

| AI Dev OS | 敏捷 | 变化率 |
|-----------|-------|-------------|
| L1：哲学 | 4 个核心价值观 | 几乎不变 |
| L2：决策标准 | 12 条原则 | 低 |
| L3：指南 | Scrum/XP/Kanban 实践 | 中 |
| L4：AI 框架 | Jira 工作流、CI/CD 配置 | 高 |

**关键洞察**：货物崇拜警告——在不理解 L1-L2 的情况下复制 L3-L4 会导致失败。

## 第二梯队：部分结构相似性

| 理论 | 对 AI Dev OS 的关键贡献 |
|--------|-------------------------------|
| **领域驱动设计**（Evans，2003） | 限界上下文 → 按领域划分的指南作用域 |
| **Zachman 框架**（1987） | 每一层在本质上不同，而非仅是更详细 |
| **软件产品线**（CMU SEI，2001） | 核心资产 vs. 产品特定资产；变异点 |
| **TOGAF**（The Open Group，1995） | 治理：谁可以更改哪一层 |
| **架构决策记录**（Nygard，2011） | 记录理由，而非仅是决策；替代追踪 |
| **GoF 设计模式**（1994） | 30 年的证据：抽象模式比具体模式更长寿 |
| **TRON 架构**（坂村，1984） | 按用途分离（ITRON/BTRON/CTRON）通过 HFDS 统一；工具特定层共享共同理念 |

## 6 条跨领域法则

分析所有 16 个理论揭示了 6 条普适法则：

| # | 法则 | 来源理论 |
|---|-----|-----------------|
| 1 | **依赖规则** — 上层不得引用下层 | Clean Architecture、Pattern Languages |
| 2 | **生命周期 = 抽象度** — 抽象的事物存续更久 | Clean Architecture、GoF、Alexander、Zachman |
| 3 | **不可跳层** — 成熟度是顺序的 | CMMI、敏捷（货物崇拜）、工匠精神 |
| 4 | **质的差异** — 层之间的差异是性质的，而非程度的 | Zachman、ISO 42010、Kruchten |
| 5 | **螺旋反馈** — 实践必须反馈到哲学 | SECI、Alexander |
| 6 | **可追溯性 = 生成性** — 层之间的显式链接使新情况下的推理成为可能 | Pattern Languages、ADR、GoF |

## 参考文献

- Alexander, C. (1977). *A Pattern Language*. Oxford University Press.
- Beck, K. et al. (2001). "Manifesto for Agile Software Development."
- Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.
- Gamma, E. et al. (1994). *Design Patterns*. Addison-Wesley.
- Martin, R.C. (2017). *Clean Architecture*. Prentice Hall.
- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Sakamura, K. (1984). *TRON Project*. University of Tokyo.
- Zachman, J. (1987). "A Framework for Information Systems Architecture." *IBM Systems Journal*, 26(3).

---

Languages: [English](../../../../theory/classical-theories.md) | [日本語](../../ja/theory/classical-theories.md) | 简体中文 | [한국어](../../ko/theory/classical-theories.md) | [Español](../../es/theory/classical-theories.md)

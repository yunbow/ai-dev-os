# AI 编程规则的保质期模型

## 概念

每层都有一个"保质期" — 内容需要重大修订前的预期时间段。

| 层 | 保质期 | 类比 |
|-------|-----------|---------|
| L1: Philosophy | 2-5 年 | 城市道路布局 |
| L2: Decision Criteria | 1-3 年 | 建筑设计 |
| L3: Guidelines | 6-12 个月 | 室内设计 |
| L4: AI Frames | 2-4 个月 | 家具摆放 |

## 投资策略

应最大力度投资上层，因为上层错误会向下传播：

- **L1 错误**（错误的哲学）→ 灾难性的、几乎不可见、影响一切
- **L2 错误**（错误的原则）→ 代价高昂、难以检测、影响所有代码
- **L3 错误**（错误的指南）→ 中等、可通过审查检测、影响特定模式
- **L4 错误**（错误的工具配置）→ 代价低、立即可见、容易修复

## 过期检测

使用 `git log` 检测过时内容：

```bash
# 检查每层的最后更新日期
git log -1 --format="%ci" -- 01_philosophy/
git log -1 --format="%ci" -- 02_decision-criteria/
git log -1 --format="%ci" -- 03_guidelines/
git log -1 --format="%ci" -- 04_ai-frames/
```

`/ai-dev-os-audit` 命令自动化此检查。

---

Languages: [English](../../../../spec/shelf-life.md) | [日本語](../../ja/spec/shelf-life.md) | 简体中文 | [한국어](../../ko/spec/shelf-life.md) | [Español](../../es/spec/shelf-life.md)

# AI Dev OS — 运维指南

本文档涵盖 **ai-dev-os 核心仓库**（规范、理论、入门指南）的运维。

各组件的运维指南请参阅：

- **规则**：各规则仓库的 `docs/operation-guide.md`
- **插件**：各插件仓库的 `docs/operation-guide.md`

---

## 1. 仓库结构

```text
ai-dev-os/
├── spec/                        # 框架规范
├── theory/                      # 理论背景
├── getting-started/             # 入门指南
└── docs/                        # 本指南 + 多语言版
```

本仓库仅包含 AI Dev OS 框架的**规范和理论**。实际的指南文件位于规则仓库中：

- [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript)
- [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python)

---

## 2. 更新策略

### 2.1 何时更新

| 部分 | 更新触发 | 频率 |
|---------|---------------|-----------|
| `spec/` | 4 层模型设计变更、新设计原则 | 极少 |
| `theory/` | 新理论关联、更新研究引用 | 少 |
| `getting-started/` | 新增规则/插件、生态变更 | 中等 |
| `docs/` | 指南改进、新增多语言翻译 | 中等 |

### 2.2 更新规则

- **spec/**：此处的变更影响整个生态系统。视为 MAJOR 版本变更。
- **theory/**：学术引用和理论分析。保持事实准确，注明引用来源。
- **getting-started/**：必须与最新的规则/插件仓库保持同步。
- 添加新的规则仓库或插件时，需更新：
  - `README.md`（生态系统表、入门部分）
  - `getting-started/choose-rules.md` 或 `getting-started/choose-plugin.md`

---

## 3. 版本管理

使用语义化版本（git 标签）管理。

| 变更类型 | 版本 | 示例 |
|-------------|---------|--------|
| 基础规范变更（4 层模型重新设计） | MAJOR | v2.0.0 |
| 新增理论文档、入门指南更新 | MINOR | v1.1.0 |
| 拼写修正、措辞改进 | PATCH | v1.0.1 |

---

## 4. 语言策略

- 本仓库所有内容以**英语**编写
- 多语言运维指南维护在 `docs/i18n/`（JA, ZH-CN, KO, ES）
- README.md 的多语言翻译位于 `docs/i18n/{lang}/README.md`

---

Languages: [English](../../operation-guide.md) | [日本語](../ja/operation-guide.md) | 简体中文 | [한국어](../ko/operation-guide.md) | [Español](../es/operation-guide.md)

# 选择规则

## 可用规则集

| 仓库 | 语言 | 框架 |
|---|---|---|
| [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript | Next.js (App Router), Node.js CLI |
| [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python | FastAPI, Flask, Typer CLI |

## 规则集内容

每个规则集包含完整的 4 层结构：

```
ai-dev-os-rules-{language}/
├── 01_philosophy/               # L1：设计哲学（示例，请用自己的语言重写）
├── 02_decision-criteria/        # L2：判断标准（示例，请用自己的语言重写）
├── 03_guidelines/               # L3：指南
│   ├── common/                  #   语言无关规则（13 个文件）
│   └── frameworks/              #   框架特定规则
├── 04_ai-prompts/               # L4：AI 提示和技能
└── templates/                   # 项目脚手架模板
```

## 如果没有对应的语言

1. Fork [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) 作为起点
2. 保留 `01_philosophy/`、`02_decision-criteria/` 和 `03_guidelines/common/`（这些是语言无关的）
3. 将 `03_guidelines/frameworks/` 替换为您的框架指南
4. 更新 `04_ai-prompts/` 和 `templates/` 以适配您的技术栈

---

Languages: [English](../../../../getting-started/choose-rules.md) | [日本語](../../ja/getting-started/choose-rules.md) | 简体中文 | [한국어](../../ko/getting-started/choose-rules.md) | [Español](../../es/getting-started/choose-rules.md)

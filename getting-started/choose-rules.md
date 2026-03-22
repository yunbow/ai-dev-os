# Choosing Your Rules

## Available Rule Sets

| Repository | Language | Frameworks |
|---|---|---|
| [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript | Next.js (App Router), Node.js CLI |
| [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python | FastAPI, Flask, Typer CLI |

## What's Inside a Rule Set

Each rule set contains the full 4-layer structure:

```text
ai-dev-os-rules-{language}/
├── 01_philosophy/               # L1: Design Philosophy (sample, rewrite in your language)
├── 02_decision-criteria/        # L2: Decision Criteria (sample, rewrite in your language)
├── 03_guidelines/               # L3: Guidelines
│   ├── common/                  #   Language-independent rules (13 files)
│   └── frameworks/              #   Framework-specific rules
├── 04_ai-prompts/               # L4: AI Prompts & Skills
└── templates/                   # Project scaffolding templates
```

## If Your Language is Not Available

1. Fork [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) as a starting point
2. Keep `01_philosophy/`, `02_decision-criteria/`, and `03_guidelines/common/` (these are language-independent)
3. Replace `03_guidelines/frameworks/` with your framework's guidelines
4. Update `04_ai-prompts/` and `templates/` for your stack

---

Languages: English | [日本語](../docs/i18n/ja/getting-started/choose-rules.md) | [简体中文](../docs/i18n/zh-CN/getting-started/choose-rules.md) | [한국어](../docs/i18n/ko/getting-started/choose-rules.md) | [Español](../docs/i18n/es/getting-started/choose-rules.md)

# AI Dev OS — Operation Guide

English | [日本語](i18n/ja/operation-guide.md) | [简体中文](i18n/zh-CN/operation-guide.md) | [한국어](i18n/ko/operation-guide.md) | [Español](i18n/es/operation-guide.md)

This document covers the operation of the **ai-dev-os core repository** (specification, theory, getting-started guide).

For operation guides on specific components, see:

- **Rules**: Each rules repository has its own `docs/operation-guide.md`
- **Plugins**: Each plugin repository has its own `docs/operation-guide.md`

---

## 1. Repository Structure

```text
ai-dev-os/
├── spec/                        # Framework specification
├── theory/                      # Theoretical background
├── getting-started/             # Getting started guides
└── docs/                        # This guide + i18n
```text

This repository contains **only the specification and theory** of the AI Dev OS framework. The actual guideline files are in the rules repositories:

- [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript)
- [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python)

---

## 2. Update Policy

### 2.1 When to Update

| Section | Update Trigger | Frequency |
|---------|---------------|-----------|
| `spec/` | 4-layer model design changes, new design principles | Very rare |
| `theory/` | New theoretical connections, updated research references | Rare |
| `getting-started/` | New rules/plugins added, ecosystem changes | Medium |
| `docs/` | Guide improvements, new i18n translations | Medium |

### 2.2 Rules for Updates

- **spec/**: Changes here affect the entire ecosystem. Treat as MAJOR version changes.
- **theory/**: Academic references and theoretical analysis. Keep factual and well-cited.
- **getting-started/**: Must stay in sync with the latest rules/plugin repositories.
- When adding a new rules repository or plugin, update:
  - `README.md` (Ecosystem table, Getting Started section)
  - `getting-started/choose-rules.md` or `getting-started/choose-plugin.md`

---

## 3. Versioning

Managed with semantic versioning (git tags).

| Change Type | Version | Example |
|-------------|---------|--------|
| Fundamental spec changes (4-layer model redesign) | MAJOR | v2.0.0 |
| New theory documents, getting-started updates | MINOR | v1.1.0 |
| Typo fixes, wording improvements | PATCH | v1.0.1 |

---

## 4. Language Policy

- All content in this repository is written in **English**
- Multilingual operation guides are maintained in `docs/i18n/` (JA, ZH-CN, KO, ES)
- README.md i18n translations are in `docs/i18n/{lang}/README.md`

# Shelf-Life Model for AI Coding Rules

## Concept

Each layer has a "shelf life" — the expected period before the content needs significant revision.

| Layer | Shelf Life | Analogy |
|-------|-----------|---------|
| L1: Philosophy | 2-5 years | City road layout |
| L2: Decision Criteria | 1-3 years | Building architecture |
| L3: Guidelines | 6-12 months | Interior design |
| L4: AI Frames | 2-4 months | Furniture arrangement |

## Investment Strategy

Invest most heavily in upper layers, because errors compound downward:

- **L1 error** (wrong philosophy) → catastrophic, nearly invisible, affects everything
- **L2 error** (wrong principle) → expensive, hard to detect, affects all code
- **L3 error** (wrong guideline) → moderate, detectable by review, affects specific patterns
- **L4 error** (wrong tool config) → cheap, immediately visible, easily fixed

## Expiration Detection

Use `git log` to detect staleness:

```bash
# Check last update date for each layer
git log -1 --format="%ci" -- 01_philosophy/
git log -1 --format="%ci" -- 02_decision-criteria/
git log -1 --format="%ci" -- 03_guidelines/
git log -1 --format="%ci" -- 04_ai-frames/
```

The `/ai-dev-os-audit` command automates this check.

---

Languages: English | [日本語](../docs/i18n/ja/spec/shelf-life.md) | [简体中文](../docs/i18n/zh-CN/spec/shelf-life.md) | [한국어](../docs/i18n/ko/spec/shelf-life.md) | [Español](../docs/i18n/es/spec/shelf-life.md)

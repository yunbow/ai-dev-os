# Specificity Cascade for AI Coding Rules

## CSS Specificity Analogy

AI Dev OS resolves rule conflicts using the Specificity Cascade, inspired by CSS specificity:

```
1. [Highest] frameworks/[stack]/*   ← Most specific
2. [High]    common/*               ← Common but concrete
3. [Medium]  project-specific/*     ← Project context
4. [Low]     02_decision-criteria/* ← Abstract criteria
5. [Lowest]  01_philosophy/*        ← Most abstract
```

> **Note**: `project-specific/*` refers to guidelines in the user's project (e.g., `docs/guidelines/billing.md`), NOT in the rules repository. The rules repository contains only `frameworks/` and `common/`. Project-specific guidelines are created by the user for domain logic, external integrations, legal requirements, etc.

## How It Works

1. When coding, the AI first looks for **framework-specific** rules (most specific)
2. If no framework rule exists, fall back to **common** rules
3. If no common rule exists, fall back to **project-specific** conventions
4. If nothing explicit exists, apply **decision criteria** to reason about the best approach
5. As a last resort, fall back to **philosophy** for value-based judgment

## Example: Error Handling

Suppose the AI encounters an error handling decision in a Next.js Server Action:

1. **frameworks/nextjs/server-actions.md** says "Use ActionResult<T> pattern" → **Apply this**
2. **common/error-handling.md** says "Classify errors into user/system/validation" → Also apply
3. **02_decision-criteria/error-strategy.md** says "Prefer explicit error types over exceptions" → Informs the approach
4. **01_philosophy/principles.md** says "Correctness over convenience" → Underlying value

All layers contribute, but the most specific rule wins when there is a conflict.

---

Languages: English | [日本語](../docs/i18n/ja/spec/priority-cascade.md) | [简体中文](../docs/i18n/zh-CN/spec/priority-cascade.md) | [한국어](../docs/i18n/ko/spec/priority-cascade.md) | [Español](../docs/i18n/es/spec/priority-cascade.md)

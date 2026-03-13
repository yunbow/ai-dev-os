# Tacit-to-Explicit Engineering

## The Core Problem

> AI-generated code is "almost right but subtly wrong" — 66% of developers cite this as their biggest frustration.

The root cause is not insufficient prompting or poor AI models. It is that **senior developers' tacit knowledge has not been converted to explicit, enforceable rules**.

## What is Tacit Knowledge?

Tacit knowledge (暗黙知) is knowledge that is difficult to articulate:

- "This code doesn't feel right" → What specific rule is being violated?
- "We don't do it that way here" → Where is "that way" documented?
- "Any senior engineer would know this" → But the AI is not a senior engineer

## The SECI Model Connection

AI Dev OS maps directly to Ikujiro Nonaka's SECI model of knowledge creation (1995):

| SECI Phase | AI Dev OS Layer | Knowledge Flow |
|-----------|----------------|----------------|
| Socialization (共同化) | L1: Philosophy | Tacit → Tacit: Shared through experience |
| Externalization (表出化) | L2: Decision Criteria | Tacit → Explicit: Articulated as principles |
| Combination (連結化) | L3: Guidelines | Explicit → Explicit: Organized into rules |
| Internalization (内面化) | L4: AI Frames | Explicit → Tacit: Embodied through practice |

The key insight: **AI Dev OS is a knowledge creation system, not just a documentation hierarchy.**

## The Spiral

The SECI model is a spiral, not a one-way process:

```
L4 practice → discovers new tacit knowledge → L1 evolves
     ↑                                              ↓
     └──── L3 rules ← L2 principles ← L1 values ──┘
```

The `/ai-dev-os-evolve` command implements this spiral by analyzing recent coding practices and proposing updates to L1-L2.

## Why AI-Generated Code Falls Short in Specific Areas

AI coding assistants produce code that is generally competent — correct syntax, working logic, reasonable structure. But they systematically underperform in areas where **implicit team knowledge** is required:

**Security:** AI generates code that "works" but has subtle vulnerabilities. Common examples:
- Using `Math.random()` for tokens instead of `crypto.randomBytes()` — functionally equivalent but cryptographically insecure
- Interpolating user input into email templates without HTML escaping — no runtime error, but XSS vector
- Implementing auth endpoints without rate limiting — the feature works, but is vulnerable to brute force

**Logging & Observability:** AI adds `console.log` but rarely implements structured logging with request IDs, error classification, or audit trails. These patterns are team-specific and rarely appear in training data as a unified system.

**Project conventions:** Error boundary placement, directory structure, naming patterns (handle+noun+verb), type assertion minimization — these are team decisions, not universal best practices.

**Why this happens:** AI models are trained on public code which represents the **average** of all codebases. Your team's specific standards — especially security hardening and observability — are above average by definition, and therefore underrepresented in training data.

## Why This Matters

Without explicit rules:
- AI generates code that **looks correct but violates team norms**
- Code review becomes a **repeated teaching session** for the same issues
- Knowledge **leaves when people leave** — the AI never learned it

With AI Dev OS:
- Tacit knowledge is captured as explicit, versioned, enforceable rules
- The AI **improves with every code review** (via Rule Harvesting)
- Knowledge **survives team changes** and tool migrations

## References

- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Nonaka, I. & Konno, N. (1998). "The Concept of 'Ba'." *California Management Review*, 40(3).

---

Languages: English | [日本語](../docs/i18n/ja/theory/tacit-to-explicit.md) | [简体中文](../docs/i18n/zh-CN/theory/tacit-to-explicit.md) | [한국어](../docs/i18n/ko/theory/tacit-to-explicit.md) | [Español](../docs/i18n/es/theory/tacit-to-explicit.md)

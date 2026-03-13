# Classical Software Engineering Theories

## Overview

AI Dev OS's 4-layer model is not a novel invention — it maps to patterns observed across 15 established software engineering theories spanning 50 years.

## Tier 1: Direct Structural Similarity

### Clean Architecture (Robert C. Martin, 2012/2017)

| AI Dev OS | Clean Architecture | Stability |
|-----------|-------------------|-----------|
| L1: Philosophy | Entities (Business Rules) | Highest |
| L2: Decision Criteria | Use Cases (Application Rules) | High |
| L3: Guidelines | Interface Adapters | Medium |
| L4: AI Frames | Frameworks & Drivers | Lowest |

**Key insight**: The dependency rule — source code dependencies must point inward.

### Pattern Languages (Christopher Alexander, 1977)

| AI Dev OS | Pattern Language | Scale |
|-----------|----------------|-------|
| L1: Philosophy | "Quality Without a Name" | City |
| L2: Decision Criteria | Large-scale patterns | District |
| L3: Guidelines | Medium-scale patterns | Building |
| L4: AI Frames | Small-scale patterns | Materials |

**Key insight**: Larger patterns are longer-lived. Abstract patterns generate concrete ones.

### SECI Model (Nonaka & Takeuchi, 1995)

| AI Dev OS | SECI | Knowledge Flow |
|-----------|------|----------------|
| L1: Philosophy | Socialization | Tacit → Tacit |
| L2: Decision Criteria | Externalization | Tacit → Explicit |
| L3: Guidelines | Combination | Explicit → Explicit |
| L4: AI Frames | Internalization | Explicit → Tacit |

**Key insight**: Knowledge creation is a spiral, not linear. Practice feeds back to philosophy.

### Agile Manifesto (2001)

| AI Dev OS | Agile | Change Rate |
|-----------|-------|-------------|
| L1: Philosophy | 4 Core Values | Nearly immutable |
| L2: Decision Criteria | 12 Principles | Low |
| L3: Guidelines | Scrum/XP/Kanban Practices | Medium |
| L4: AI Frames | Jira Workflows, CI/CD Config | High |

**Key insight**: Cargo cult warning — copying L3-L4 without understanding L1-L2 leads to failure.

## Tier 2: Partial Structural Similarity

| Theory | Key Contribution to AI Dev OS |
|--------|-------------------------------|
| **Domain-Driven Design** (Evans, 2003) | Bounded Context → Scoped guidelines per domain |
| **Zachman Framework** (1987) | Each layer is qualitatively different, not just more detailed |
| **Software Product Lines** (CMU SEI, 2001) | Core assets vs. product-specific assets; variation points |
| **TOGAF** (The Open Group, 1995) | Governance: who can change which layer |
| **Architecture Decision Records** (Nygard, 2011) | Record rationale, not just decisions; supersession tracking |
| **GoF Design Patterns** (1994) | 30 years of evidence: abstract patterns outlive concrete ones |

## The 6 Cross-Cutting Laws

Analyzing all 15 theories reveals 6 universal laws:

| # | Law | Source Theories |
|---|-----|-----------------|
| 1 | **Dependency Rule** — Upper layers must not reference lower layers | Clean Architecture, Pattern Languages |
| 2 | **Lifespan = Abstraction** — Abstract things live longer | Clean Architecture, GoF, Alexander, Zachman |
| 3 | **No Layer Skipping** — Maturity is sequential | CMMI, Agile (cargo cult), Craftsmanship |
| 4 | **Qualitative Difference** — Layers differ in kind, not degree | Zachman, ISO 42010, Kruchten |
| 5 | **Spiral Feedback** — Practice must feed back to philosophy | SECI, Alexander |
| 6 | **Traceability = Generativity** — Explicit links between layers enable inference in novel situations | Pattern Languages, ADR, GoF |

## References

- Alexander, C. (1977). *A Pattern Language*. Oxford University Press.
- Beck, K. et al. (2001). "Manifesto for Agile Software Development."
- Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.
- Gamma, E. et al. (1994). *Design Patterns*. Addison-Wesley.
- Martin, R.C. (2017). *Clean Architecture*. Prentice Hall.
- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Zachman, J. (1987). "A Framework for Information Systems Architecture." *IBM Systems Journal*, 26(3).

---

Languages: English | [日本語](../docs/i18n/ja/theory/classical-theories.md) | [简体中文](../docs/i18n/zh-CN/theory/classical-theories.md) | [한국어](../docs/i18n/ko/theory/classical-theories.md) | [Español](../docs/i18n/es/theory/classical-theories.md)

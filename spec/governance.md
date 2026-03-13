# Governance Model

> Defines who can change what, and how changes are reviewed.

## Rule Change Authority

| Layer | Who Can Change | Review Required | Rationale |
|-------|---------------|-----------------|-----------|
| **L1: Philosophy** | Tech Lead / Architect | Full team consensus | Changes affect every decision downstream. Rare (once per year or less). |
| **L2: Decision Criteria** | Tech Lead / Architect | Architect review + 1 senior | Sets boundaries for all implementation rules. |
| **L3: Guidelines** | Any developer | Domain owner review | Concrete rules that evolve with the codebase. Most frequent changes. |
| **L4: AI Frames** | Any developer | Self or peer review | Tool-specific configurations. Low blast radius. |

## Change Process

### Proposing a New Rule

1. **Observe** — Identify a recurring problem in AI-generated code
2. **Extract** — Use `ai-dev-os-extract` to draft the rule
3. **Propose** — Open a PR with the new rule in the appropriate guideline file
4. **Review** — Domain owner reviews for clarity, correctness, and non-duplication
5. **Merge** — Rule is active after merge. Tag as `[draft]` initially.

### Modifying L1/L2

L1 and L2 changes require a written rationale explaining:
- What changed and why
- Impact on existing L3 guidelines
- Whether any L3 rules need updating as a consequence

### Deprecating a Rule

1. Tag the rule as `[deprecated]` with a reason
2. Keep the rule visible for one release cycle
3. Remove in the next guideline update

## Scaling Guidelines

| Team Size | Recommended Governance |
|-----------|----------------------|
| 1-3 developers | Informal. Author reviews their own L3/L4 changes. |
| 4-10 developers | Assign domain owners for L3 areas (e.g., security, API design). L1/L2 changes need tech lead approval. |
| 10+ developers | Formal RFC process for L1/L2. L3 changes require domain owner + 1 reviewer. Consider a quarterly "rule review" meeting. |

## Conflict Resolution

When team members disagree on a rule:

1. Check the priority cascade — higher-specificity rules win
2. Check L2 decision criteria — they should resolve most ambiguities
3. If L2 doesn't resolve it, escalate to L1 philosophy
4. If still unresolved, the architect makes the call and documents the decision in L2

# Retrofitting AI Dev OS into Existing Projects

> How to adopt AI Dev OS in a codebase that already has 5,000+ lines of code.

## Overview

AI Dev OS can be adopted incrementally. You do not need to fix every existing violation before benefiting from the framework. The strategy is: **set up the structure, assess the current state, then improve incrementally**.

## Step-by-Step Adoption

### Step 1: Install (30 minutes)

Follow the standard [Quick Start](./quick-start.md) to add rules and plugin as submodules. This does not change any existing code.

### Step 2: Assess Current State (1 hour)

Run a full project scan to understand your baseline:

```text
/ai-dev-os-scan
```

This will produce a violation report. **Do not try to fix everything at once.** The report is your baseline, not your to-do list.

### Step 3: Prioritize (30 minutes)

From the scan results, identify the **top 3 guideline areas** with the most impact:

| Priority | Criteria |
|----------|----------|
| **Fix first** | Security violations, authentication gaps, input validation |
| **Fix second** | Error handling inconsistencies, naming convention drift |
| **Fix later** | Code structure, performance patterns, documentation |

### Step 4: Configure Static Context

Create your CLAUDE.md with only the guidelines relevant to your top 3 priority areas. Do not include all guidelines — start small.

```markdown
# Project Guidelines

## References
- docs/ai-dev-os/03_guidelines/common/security.md
- docs/ai-dev-os/03_guidelines/common/error-handling.md
- docs/ai-dev-os/03_guidelines/common/naming.md
```

### Step 5: Apply to New Code Only

Configure your workflow so that AI Dev OS checks apply to **new and modified code only**, not the entire codebase:

```text
/ai-dev-os-check
```

This checks only `git diff` — files you haven't touched are not flagged.

### Step 6: Expand Gradually

Every 2-4 weeks:

1. Run `/ai-dev-os-scan` to measure progress
2. Add 1-2 more guideline references to CLAUDE.md
3. Use `/ai-dev-os-extract` to capture project-specific patterns
4. After 2-3 months, run `/ai-dev-os-audit` for a full health check

## Anti-Patterns

| Don't | Do Instead |
|-------|-----------|
| Fix all violations in one PR | Fix violations as you touch each file |
| Add all 30+ guidelines to CLAUDE.md on day 1 | Start with 3-5 most impactful guidelines |
| Rewrite existing code to match guidelines | Apply guidelines to new code; refactor existing code opportunistically |
| Block PRs on legacy code violations | Only enforce guidelines on changed lines |

## Timeline Expectation

| Week | Activity |
|------|----------|
| Week 1 | Install + initial scan + top 3 priorities |
| Week 2-4 | Apply to new code, extract project-specific rules |
| Month 2-3 | Expand guideline coverage, start L2 principles |
| Month 3+ | Full coverage, periodic audits, SECI evolution |

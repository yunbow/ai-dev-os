# Choosing Your Plugin

## Available Plugins

| Tool | Repository | Features |
|---|---|---|
| [Claude Code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Skills (slash commands), Hooks, Sub-agents | Full automation with lifecycle hooks |
| [Kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Steering Rules, Hooks | Auto/manual/fileMatch activation modes |
| [Cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Rules (.mdc) | File-scoped and agent-requested rules |

## Feature Comparison

| Feature | Claude Code | Kiro | Cursor |
|---------|------------|------|--------|
| Setup wizard | `/ai-dev-os-init` | `#ai-dev-os-init` | `@ai-dev-os-init` |
| Diff check | `/ai-dev-os-check` | `#ai-dev-os-check` | `@ai-dev-os-check` |
| Full scan | `/ai-dev-os-scan` | `#ai-dev-os-scan` | `@ai-dev-os-scan` |
| Rule extraction | `/ai-dev-os-extract` | `#ai-dev-os-extract` | `@ai-dev-os-extract` |
| Implementation plan | `/ai-dev-os-plan` | `#ai-dev-os-plan` | `@ai-dev-os-plan` |
| Rule explainer | `/ai-dev-os-why` | `#ai-dev-os-why` | `@ai-dev-os-why` |
| Health audit | `/ai-dev-os-audit` | `#ai-dev-os-audit` | `@ai-dev-os-audit` |
| SECI evolution | `/ai-dev-os-evolve` | `#ai-dev-os-evolve` | `@ai-dev-os-evolve` |
| Compliance report | `/ai-dev-os-report` | `#ai-dev-os-report` | `@ai-dev-os-report` |
| Ticket generation | `/ai-dev-os-ticket` | `#ai-dev-os-ticket` | `@ai-dev-os-ticket` |
| Pre-commit hook | ✅ | ✅ | — |
| File-save hook | — | ✅ | — |
| Auto code check | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| L1-L2 dependency warning | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| Sub-agents | ✅ (3 agents) | — | — |

## If Your Tool is Not Listed

The 4-layer guidelines (L1-L3) work with any AI coding tool. Only L4 (AI Frames) is tool-specific. You can:

1. Use the rules repository directly and reference guidelines from your tool's configuration file
2. Refer to the plugin repositories as examples for creating your own integration

---

Languages: English | [日本語](../docs/i18n/ja/getting-started/choose-plugin.md) | [简体中文](../docs/i18n/zh-CN/getting-started/choose-plugin.md) | [한국어](../docs/i18n/ko/getting-started/choose-plugin.md) | [Español](../docs/i18n/es/getting-started/choose-plugin.md)

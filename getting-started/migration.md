# Tool Migration Guide

## Overview

AI Dev OS's 4-layer model ensures that **75% of your investment (L1-L3)** survives tool migrations. Only **L4 (25%)** — the plugin — needs to change.

## Migration Steps

### From Claude Code to Kiro

1. **Keep**: `docs/ai-dev-os/` submodule (L1-L3 rules) — no changes needed
2. **Remove**: `.claude/plugins/ai-dev-os/` submodule
3. **Add**: Kiro plugin

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-kiro.git .kiro/plugins/ai-dev-os
   cp -r .kiro/plugins/ai-dev-os/steering/ .kiro/steering/
   cp -r .kiro/plugins/ai-dev-os/hooks/ .kiro/hooks/
   ```

4. **Convert**: CLAUDE.md → AGENTS.md (same content, Kiro reads AGENTS.md)

   ```bash
   cp CLAUDE.md AGENTS.md
   ```

5. **Verify**: Run `#ai-dev-os-init` in Kiro to confirm setup

### From Claude Code to Cursor

1. **Keep**: `docs/ai-dev-os/` submodule — no changes needed
2. **Remove**: `.claude/plugins/ai-dev-os/` submodule
3. **Add**: Cursor plugin

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
   cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/
   ```

4. **Convert**: CLAUDE.md → .cursorrules

   ```bash
   cp CLAUDE.md .cursorrules
   ```

5. **Verify**: Run `@ai-dev-os-init` in Cursor to confirm setup

### From Kiro to Claude Code

1. **Keep**: `docs/ai-dev-os/` submodule — no changes needed
2. **Remove**: `.kiro/steering/ai-dev-os-*` files and hooks
3. **Add**: Claude Code plugin

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```

4. **Convert**: AGENTS.md → CLAUDE.md

   ```bash
   cp AGENTS.md CLAUDE.md
   ```

5. **Verify**: Run `/ai-dev-os-init`

### From Cursor to Claude Code

1. **Keep**: `docs/ai-dev-os/` submodule — no changes needed
2. **Remove**: `.cursor/rules/ai-dev-os-*` files
3. **Add**: Claude Code plugin

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```

4. **Convert**: .cursorrules → CLAUDE.md

   ```bash
   cp .cursorrules CLAUDE.md
   ```

5. **Verify**: Run `/ai-dev-os-init`

## What Transfers (75%)

| Layer | Content | Transfers? |
|-------|---------|-----------|
| L1: Philosophy | `01_philosophy/` | ✅ 100% — no changes |
| L2: Decision Criteria | `02_decision-criteria/` | ✅ 100% — no changes |
| L3: Guidelines | `03_guidelines/` | ✅ 100% — no changes |
| L4: AI Frames | Plugin-specific | ❌ Replace with new plugin |
| Context file | CLAUDE.md / AGENTS.md / .cursorrules | ⚠️ Copy and rename |

## What Does NOT Transfer

- Plugin-specific hooks configuration
- Tool-specific skill invocation syntax (`/` vs `#` vs `@`)
- CI/CD integrations that reference specific tool commands

---

Languages: English | [日本語](../docs/i18n/ja/getting-started/migration.md) | [简体中文](../docs/i18n/zh-CN/getting-started/migration.md) | [한국어](../docs/i18n/ko/getting-started/migration.md) | [Español](../docs/i18n/es/getting-started/migration.md)

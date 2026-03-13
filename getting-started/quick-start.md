# Quick Start Guide

## Fastest Way: CLI

```bash
# Interactive — prompts for language and tool
npx ai-dev-os init

# Or specify directly:
npx ai-dev-os init --rules typescript --plugin claude-code
npx ai-dev-os init --rules python --plugin kiro
npx ai-dev-os init --rules typescript --plugin cursor
```

> Adds submodules, copies templates, and merges hooks in one command.
> See [AI Dev OS CLI](https://github.com/yunbow/ai-dev-os-cli) for all options.

---

## Manual Setup

### Choose Your Language Rules

| Language | Repository | Command |
|---|---|---|
| TypeScript / Next.js | [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os` |
| Python / FastAPI | [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os` |

## Choose Your Tool Plugin

| Tool | Repository | Setup |
|---|---|---|
| Claude Code | [ai-dev-os-plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | `git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os` |
| Kiro | [ai-dev-os-plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Copy steering rules to `.kiro/steering/` |
| Cursor | [ai-dev-os-plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Copy rules to `.cursor/rules/` |

## Example: TypeScript + Claude Code

```bash
cd /path/to/your-project

# 1. Add rules
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. Add plugin
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. Set up CLAUDE.md
cp docs/ai-dev-os/templates/nextjs/CLAUDE.md.template ./CLAUDE.md

# 4. Run setup wizard (type in Claude Code chat, not in terminal)
# /ai-dev-os-init
```

## Example: Python + Claude Code

```bash
cd /path/to/your-project

# 1. Add rules
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. Add plugin
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. Set up CLAUDE.md
cp docs/ai-dev-os/templates/python-cli/CLAUDE.md.template ./CLAUDE.md

# 4. Run setup wizard (type in Claude Code chat, not in terminal)
# /ai-dev-os-init
```

## Example: Python + Kiro

```bash
cd /path/to/your-project

# 1. Add rules
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. Add plugin
git clone https://github.com/yunbow/ai-dev-os-plugin-kiro.git
cp -r ai-dev-os-plugin-kiro/steering/ .kiro/steering/
cp -r ai-dev-os-plugin-kiro/hooks/ .kiro/hooks/
rm -rf ai-dev-os-plugin-kiro  # Clean up cloned directory

# 3. Run setup wizard (type in Kiro chat, not in terminal)
# #ai-dev-os-init
```

## Example: TypeScript + Cursor

```bash
cd /path/to/your-project

# 1. Add rules
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. Add plugin
git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/

# 3. Run setup wizard (type in Cursor chat, not in terminal)
# @ai-dev-os-init
```

## Update Rules

```bash
git submodule update --remote docs/ai-dev-os
```

## Pin to a Specific Version

```bash
cd docs/ai-dev-os
git checkout v1.2.0
cd ../..
git add docs/ai-dev-os
git commit -m "chore: pin ai-dev-os to v1.2.0"
```

## Submodule Troubleshooting

| Problem | Solution |
|---------|----------|
| Empty `docs/ai-dev-os/` directory after `git clone` | Run `git submodule update --init --recursive` |
| Submodule shows `(not initialized)` | Run `git submodule init && git submodule update` |
| CI pipeline fails with missing files | Add `git submodule update --init --recursive` to CI setup step |
| Want to always clone with submodules | Use `git clone --recurse-submodules <url>` |
| Submodule points to old commit | Run `git submodule update --remote docs/ai-dev-os` to pull latest |

---

Languages: English | [日本語](../docs/i18n/ja/getting-started/quick-start.md) | [简体中文](../docs/i18n/zh-CN/getting-started/quick-start.md) | [한국어](../docs/i18n/ko/getting-started/quick-start.md) | [Español](../docs/i18n/es/getting-started/quick-start.md)

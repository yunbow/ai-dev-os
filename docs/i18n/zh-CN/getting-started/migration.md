# 工具迁移指南

## 概述

AI Dev OS 的 4 层模型确保**75% 的投资（L1-L3）**在工具迁移中得以保留。只有 **L4（25%）**— 插件部分 — 需要更换。

## 迁移步骤

### 从 Claude Code 迁移到 Kiro

1. **保留**：`docs/ai-dev-os/` submodule（L1-L3 规则）— 无需更改
2. **移除**：`.claude/plugins/ai-dev-os/` submodule
3. **添加**：Kiro 插件

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-kiro.git .kiro/plugins/ai-dev-os
   cp -r .kiro/plugins/ai-dev-os/steering/ .kiro/steering/
   cp -r .kiro/plugins/ai-dev-os/hooks/ .kiro/hooks/
   ```

4. **转换**：CLAUDE.md → AGENTS.md（内容相同，Kiro 读取 AGENTS.md）

   ```bash
   cp CLAUDE.md AGENTS.md
   ```

5. **验证**：在 Kiro 中运行 `#ai-dev-os-init` 确认设置

### 从 Claude Code 迁移到 Cursor

1. **保留**：`docs/ai-dev-os/` submodule — 无需更改
2. **移除**：`.claude/plugins/ai-dev-os/` submodule
3. **添加**：Cursor 插件

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
   cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/
   ```

4. **转换**：CLAUDE.md → .cursorrules

   ```bash
   cp CLAUDE.md .cursorrules
   ```

5. **验证**：在 Cursor 中运行 `@ai-dev-os-init` 确认设置

### 从 Kiro 迁移到 Claude Code

1. **保留**：`docs/ai-dev-os/` submodule — 无需更改
2. **移除**：`.kiro/steering/ai-dev-os-*` 文件和 hooks
3. **添加**：Claude Code 插件

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```

4. **转换**：AGENTS.md → CLAUDE.md

   ```bash
   cp AGENTS.md CLAUDE.md
   ```

5. **验证**：运行 `/ai-dev-os-init`

### 从 Cursor 迁移到 Claude Code

1. **保留**：`docs/ai-dev-os/` submodule — 无需更改
2. **移除**：`.cursor/rules/ai-dev-os-*` 文件
3. **添加**：Claude Code 插件

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```

4. **转换**：.cursorrules → CLAUDE.md

   ```bash
   cp .cursorrules CLAUDE.md
   ```

5. **验证**：运行 `/ai-dev-os-init`

## 可迁移的内容（75%）

| 层 | 内容 | 是否迁移 |
|-------|---------|-----------|
| L1：哲学 | `01_philosophy/` | ✅ 100% — 无需更改 |
| L2：判断标准 | `02_decision-criteria/` | ✅ 100% — 无需更改 |
| L3：指南 | `03_guidelines/` | ✅ 100% — 无需更改 |
| L4：AI 框架 | 插件特定 | ❌ 替换为新插件 |
| 上下文文件 | CLAUDE.md / AGENTS.md / .cursorrules | ⚠️ 复制并重命名 |

## 不可迁移的内容

- 插件特定的 hooks 配置
- 工具特定的技能调用语法（`/` vs `#` vs `@`）
- 引用特定工具命令的 CI/CD 集成

---

Languages: [English](../../../../getting-started/migration.md) | [日本語](../../ja/getting-started/migration.md) | 简体中文 | [한국어](../../ko/getting-started/migration.md) | [Español](../../es/getting-started/migration.md)

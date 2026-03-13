# 快速入门指南

## 最快方式：CLI

```bash
# 交互模式 — 提示选择语言和工具
npx ai-dev-os init

# 或直接指定：
npx ai-dev-os init --rules typescript --plugin claude-code
npx ai-dev-os init --rules python --plugin kiro
npx ai-dev-os init --rules typescript --plugin cursor
```

> 一条命令完成 submodule 添加、模板复制和 hooks 合并。
> 详见 [AI Dev OS CLI](https://github.com/yunbow/ai-dev-os-cli)。

---

## 手动设置

### 选择语言规则

| 语言 | 仓库 | 命令 |
|---|---|---|
| TypeScript / Next.js | [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os` |
| Python / FastAPI | [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os` |

## 选择工具插件

| 工具 | 仓库 | 设置 |
|---|---|---|
| Claude Code | [ai-dev-os-plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | `git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os` |
| Kiro | [ai-dev-os-plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | 将 steering rules 复制到 `.kiro/steering/` |
| Cursor | [ai-dev-os-plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | 将 rules 复制到 `.cursor/rules/` |

## 示例：TypeScript + Claude Code

```bash
cd /path/to/your-project

# 1. 添加规则
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. 添加插件
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. 设置 CLAUDE.md
cp docs/ai-dev-os/templates/nextjs/CLAUDE.md.template ./CLAUDE.md

# 4. 运行设置向导（在 Claude Code 聊天中输入，不是在终端）
# /ai-dev-os-init
```

## 示例：Python + Claude Code

```bash
cd /path/to/your-project

# 1. 添加规则
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. 添加插件
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. 设置 CLAUDE.md
cp docs/ai-dev-os/templates/python-cli/CLAUDE.md.template ./CLAUDE.md

# 4. 运行设置向导（在 Claude Code 聊天中输入，不是在终端）
# /ai-dev-os-init
```

## 示例：Python + Kiro

```bash
cd /path/to/your-project

# 1. 添加规则
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. 添加插件
git clone https://github.com/yunbow/ai-dev-os-plugin-kiro.git
cp -r ai-dev-os-plugin-kiro/steering/ .kiro/steering/
cp -r ai-dev-os-plugin-kiro/hooks/ .kiro/hooks/
rm -rf ai-dev-os-plugin-kiro  # 清理克隆的目录

# 3. 运行设置向导（在 Kiro 聊天中输入，不是在终端）
# #ai-dev-os-init
```

## 示例：TypeScript + Cursor

```bash
cd /path/to/your-project

# 1. 添加规则
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. 添加插件
git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/

# 3. 运行设置向导（在 Cursor 聊天中输入，不是在终端）
# @ai-dev-os-init
```

## 更新规则

```bash
git submodule update --remote docs/ai-dev-os
```

## 固定到特定版本

```bash
cd docs/ai-dev-os
git checkout v1.2.0
cd ../..
git add docs/ai-dev-os
git commit -m "chore: pin ai-dev-os to v1.2.0"
```

## Submodule 故障排除

| 问题 | 解决方案 |
|---------|----------|
| `git clone` 后 `docs/ai-dev-os/` 目录为空 | 运行 `git submodule update --init --recursive` |
| Submodule 显示 `(not initialized)` | 运行 `git submodule init && git submodule update` |
| CI 管道因文件缺失而失败 | 在 CI 设置步骤中添加 `git submodule update --init --recursive` |
| 希望始终包含 submodule 克隆 | 使用 `git clone --recurse-submodules <url>` |
| Submodule 指向旧提交 | 运行 `git submodule update --remote docs/ai-dev-os` 拉取最新版 |

---

Languages: [English](../../../../getting-started/quick-start.md) | [日本語](../../ja/getting-started/quick-start.md) | 简体中文 | [한국어](../../ko/getting-started/quick-start.md) | [Español](../../es/getting-started/quick-start.md)

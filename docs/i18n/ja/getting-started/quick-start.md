# クイックスタートガイド

## 言語ルールを選ぶ

| 言語 | リポジトリ | コマンド |
|---|---|---|
| TypeScript / Next.js | [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os` |
| Python / FastAPI | [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os` |

## ツールプラグインを選ぶ

| ツール | リポジトリ | セットアップ |
|---|---|---|
| Claude Code | [ai-dev-os-plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | `git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os` |
| Kiro | [ai-dev-os-plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | ステアリングルールを `.kiro/steering/` にコピー |
| Cursor | [ai-dev-os-plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | ルールを `.cursor/rules/` にコピー |

## 例: TypeScript + Claude Code

```bash
cd /path/to/your-project

# 1. ルールを追加
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. プラグインを追加
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. CLAUDE.md をセットアップ
cp docs/ai-dev-os/templates/nextjs/CLAUDE.md.template ./CLAUDE.md

# 4. セットアップウィザードを実行（Claude Code チャットで入力。ターミナルではない）
# /ai-dev-os-init
```

## 例: Python + Claude Code

```bash
cd /path/to/your-project

# 1. ルールを追加
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. プラグインを追加
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. CLAUDE.md をセットアップ
cp docs/ai-dev-os/templates/python-cli/CLAUDE.md.template ./CLAUDE.md

# 4. セットアップウィザードを実行（Claude Code チャットで入力。ターミナルではない）
# /ai-dev-os-init
```

## 例: Python + Kiro

```bash
cd /path/to/your-project

# 1. ルールを追加
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. プラグインを追加
git clone https://github.com/yunbow/ai-dev-os-plugin-kiro.git
cp -r ai-dev-os-plugin-kiro/steering/ .kiro/steering/
cp -r ai-dev-os-plugin-kiro/hooks/ .kiro/hooks/

# 3. セットアップウィザードを実行（Kiro チャットで入力。ターミナルではない）
# #ai-dev-os-init
```

## ルールの更新

```bash
git submodule update --remote docs/ai-dev-os
```

## 特定バージョンに固定する

```bash
cd docs/ai-dev-os
git checkout v1.2.0
cd ../..
git add docs/ai-dev-os
git commit -m "chore: pin ai-dev-os to v1.2.0"
```

## サブモジュールのトラブルシューティング

| 問題 | 解決方法 |
|---------|----------|
| `git clone` 後に `docs/ai-dev-os/` ディレクトリが空 | `git submodule update --init --recursive` を実行 |
| サブモジュールが `(not initialized)` と表示される | `git submodule init && git submodule update` を実行 |
| CI パイプラインでファイルが見つからずに失敗する | CI のセットアップステップに `git submodule update --init --recursive` を追加 |
| 常にサブモジュール込みでクローンしたい | `git clone --recurse-submodules <url>` を使用 |
| サブモジュールが古いコミットを指している | `git submodule update --remote docs/ai-dev-os` を実行して最新を取得 |

---

Languages: [English](../../../../getting-started/quick-start.md) | 日本語 | [简体中文](../../zh-CN/getting-started/quick-start.md) | [한국어](../../ko/getting-started/quick-start.md) | [Español](../../es/getting-started/quick-start.md)

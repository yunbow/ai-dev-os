# ツール移行ガイド

## 概要

AI Dev OS の4層モデルにより、**投資の75%（L1-L3）**がツール移行後もそのまま活用できます。変更が必要なのは **L4（25%）**-- プラグイン部分のみです。

## 移行手順

### Claude Code から Kiro へ

1. **そのまま維持**: `docs/ai-dev-os/` サブモジュール（L1-L3ルール）-- 変更不要
2. **削除**: `.claude/plugins/ai-dev-os/` サブモジュール
3. **追加**: Kiro プラグイン

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-kiro.git .kiro/plugins/ai-dev-os
   cp -r .kiro/plugins/ai-dev-os/steering/ .kiro/steering/
   cp -r .kiro/plugins/ai-dev-os/hooks/ .kiro/hooks/
   ```

4. **変換**: CLAUDE.md → AGENTS.md（内容は同じ、Kiro は AGENTS.md を読み込みます）

   ```bash
   cp CLAUDE.md AGENTS.md
   ```

5. **確認**: Kiro で `#ai-dev-os-init` を実行してセットアップを確認

### Claude Code から Cursor へ

1. **そのまま維持**: `docs/ai-dev-os/` サブモジュール -- 変更不要
2. **削除**: `.claude/plugins/ai-dev-os/` サブモジュール
3. **追加**: Cursor プラグイン

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
   cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/
   ```

4. **変換**: CLAUDE.md → .cursorrules

   ```bash
   cp CLAUDE.md .cursorrules
   ```

5. **確認**: Cursor で `@ai-dev-os-init` を実行してセットアップを確認

### Kiro から Claude Code へ

1. **そのまま維持**: `docs/ai-dev-os/` サブモジュール -- 変更不要
2. **削除**: `.kiro/steering/ai-dev-os-*` ファイルとフック
3. **追加**: Claude Code プラグイン

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```

4. **変換**: AGENTS.md → CLAUDE.md

   ```bash
   cp AGENTS.md CLAUDE.md
   ```

5. **確認**: `/ai-dev-os-init` を実行

### Cursor から Claude Code へ

1. **そのまま維持**: `docs/ai-dev-os/` サブモジュール -- 変更不要
2. **削除**: `.cursor/rules/ai-dev-os-*` ファイル
3. **追加**: Claude Code プラグイン

   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```

4. **変換**: .cursorrules → CLAUDE.md

   ```bash
   cp .cursorrules CLAUDE.md
   ```

5. **確認**: `/ai-dev-os-init` を実行

## 移行で引き継がれるもの（75%）

| レイヤー | 内容 | 引き継ぎ |
|-------|---------|-----------|
| L1: 設計思想 | `01_philosophy/` | ✅ 100% -- 変更不要 |
| L2: 判断基準 | `02_decision-criteria/` | ✅ 100% -- 変更不要 |
| L3: ガイドライン | `03_guidelines/` | ✅ 100% -- 変更不要 |
| L4: AIフレーム | プラグイン固有 | ❌ 新しいプラグインに置き換え |
| コンテキストファイル | CLAUDE.md / AGENTS.md / .cursorrules | ⚠️ コピーしてリネーム |

## 引き継がれないもの

- プラグイン固有のフック設定
- ツール固有のスキル呼び出し構文（`/` vs `#` vs `@`）
- 特定のツールコマンドを参照する CI/CD 連携

---

Languages: [English](../../../../getting-started/migration.md) | 日本語 | [简体中文](../../zh-CN/getting-started/migration.md) | [한국어](../../ko/getting-started/migration.md) | [Español](../../es/getting-started/migration.md)

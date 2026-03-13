# プラグインの選び方

## 利用可能なプラグイン

| ツール | リポジトリ | 機能 |
|---|---|---|
| [Claude Code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | スキル（スラッシュコマンド）、フック、サブエージェント | ライフサイクルフックによる完全自動化 |
| [Kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | ステアリングルール、フック | 自動/手動/fileMatch の起動モード |
| [Cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | ルール (.mdc) | ファイルスコープおよびエージェントリクエストのルール |

## 機能比較

| 機能 | Claude Code | Kiro | Cursor |
|---------|------------|------|--------|
| セットアップウィザード | `/ai-dev-os-init` | `#ai-dev-os-init` | `@ai-dev-os-init` |
| 差分チェック | `/ai-dev-os-check` | `#ai-dev-os-check` | `@ai-dev-os-check` |
| フルスキャン | `/ai-dev-os-scan` | `#ai-dev-os-scan` | `@ai-dev-os-scan` |
| ルール抽出 | `/ai-dev-os-extract` | `#ai-dev-os-extract` | `@ai-dev-os-extract` |
| 実装計画 | `/ai-dev-os-plan` | `#ai-dev-os-plan` | `@ai-dev-os-plan` |
| ルール解説 | `/ai-dev-os-why` | `#ai-dev-os-why` | `@ai-dev-os-why` |
| ヘルス監査 | `/ai-dev-os-audit` | `#ai-dev-os-audit` | `@ai-dev-os-audit` |
| SECI進化 | `/ai-dev-os-evolve` | `#ai-dev-os-evolve` | `@ai-dev-os-evolve` |
| コンプライアンスレポート | `/ai-dev-os-report` | `#ai-dev-os-report` | `@ai-dev-os-report` |
| チケット生成 | `/ai-dev-os-ticket` | `#ai-dev-os-ticket` | `@ai-dev-os-ticket` |
| プリコミットフック | ✅ | ✅ | — |
| ファイル保存フック | — | ✅ | — |
| 自動コードチェック | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| L1-L2 依存警告 | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| サブエージェント | ✅ (3エージェント) | — | — |

## 使用するツールがリストにない場合

4層ガイドライン（L1-L3）はどのAIコーディングツールでも利用できます。ツール固有なのはL4（AIフレーム）のみです。以下の方法で対応できます:

1. ルールリポジトリを直接使用し、ツールの設定ファイルからガイドラインを参照する
2. プラグインリポジトリを参考にして、独自のインテグレーションを作成する

---

Languages: [English](../../../../getting-started/choose-plugin.md) | 日本語 | [简体中文](../../zh-CN/getting-started/choose-plugin.md) | [한국어](../../ko/getting-started/choose-plugin.md) | [Español](../../es/getting-started/choose-plugin.md)

# AI Dev OS

[![Lint & Link Check](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml/badge.svg)](https://github.com/yunbow/ai-dev-os/actions/workflows/lint.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](../../../LICENSE)

> 開発者の暗黙知を、AIコーディングのための明示的で強制可能なルールに変換する。

AI アシスタントのためのコーディングルールフレームワーク — Claude Code、Cursor、Kiro 対応

```text
> /ai-dev-os-check

## AI Dev OS Check & Fix Report
- Files checked: 12
- ✅ Passed: 45 / 🔧 Fixed: 3 / ⚠️ Manual Review: 1

| # | File              | Rule         | What was fixed              |
|---|-------------------|--------------|-----------------------------|
| 1 | route.ts:42       | security.md  | Added rate limiting         |
| 2 | user-card.tsx:7   | naming.md    | Renamed to kebab-case       |
| 3 | action.ts:15      | validation.md| Added .refine() for dueDate |
```

## なぜ AI Dev OS か？

AIが書くコードは一見正しく見えますが、チームの規約に違反しています。
コーディング標準はシニア開発者の頭の中にあり、AIのコンテキストには含まれていません。

AI Dev OS は暗黙知を形式知にすることでこの問題を解決します:

- **75%がツール移行に耐える** — ルールはツール非依存（L1〜L3）。Claude Code → Kiro → Cursor を自由に切り替え可能
- **ルールは改善され続ける** — 仮説ではなく、実際のコードレビューからルールを収穫（Rule Harvesting）
- **コストはほぼゼロ** — コンテキストに3〜5の静的ルール＋オンデマンドで包括的なチェック&修正（[ベンチマーク: 96.9/100](https://github.com/yunbow/ai-dev-os-benchmark)）
- **純粋なMarkdown** — DSLなし、コンパイルなし。すべてのルールをフォーク、修正、監査可能

AI Dev OS はAIツールを置き換えるものではなく、補完するものです。Claude Code、Kiro、Cursor がコード生成を担い、AI Dev OS はそれらが従うルールを担います。

## クイックスタート

```bash
npx ai-dev-os init
```

言語（`typescript` / `python`）とツール（`claude-code` / `kiro` / `cursor`）を選択します。

```bash
# 非対話型モード:
npx ai-dev-os init --rules typescript --plugin claude-code
```

> [CLI 詳細](https://github.com/yunbow/ai-dev-os-cli) | [手動セットアップ](getting-started/quick-start.md) | [ルールの選び方](getting-started/choose-rules.md) | [プラグインの選び方](getting-started/choose-plugin.md)

## Lifespan Layers — 4層モデル

| 層 | 名称 | ライフスパン | 目的 |
|-------|------|----------|---------|
| L1 | 哲学 | 2-5年 | ツールや言語を超越するコアバリュー |
| L2 | 判断基準 | 1-3年 | 設計とアーキテクチャの判断基準 |
| L3 | ガイドライン | 6-12ヶ月 | 具体的で検証可能なコーディングルール |
| L4 | AIフレーム | 2-4ヶ月 | ツール固有の設定とワークフロー |

上位層は抽象的で安定しており、下位層は具体的で変動しやすい。
ツールを切り替えても、L1〜L3（75%）はそのまま残り、L4だけが変わります。

## 主要コンセプト

**Specificity Cascade (rule conflict resolution)** — ルールが競合する場合、CSSの詳細度のように最も具体的なルールが優先されます。フレームワークルール > 共通ルール > プロジェクト規約 > 原則 > 哲学。[→ 詳細](spec/priority-cascade.md)

**Rule Harvesting** (bottom-up rule discovery) — ルールをトップダウンで書くのではなく、AIにコードを書かせ → レビューでギャップを発見 → ルールとして収穫する。実体験に基づくボトムアップのアプローチ。[→ 詳細](spec/4-layer-model.md#rule-harvesting)

**Guideline Capital** (guidelines as intellectual assets) — ガイドラインは使い捨てのプロンプトではなく、知的資本です。Technical Debt（負債）とは異なり、Guideline Capital は蓄積される資産です。[→ 詳細](getting-started/comparison.md)

**Two-Tier Context Strategy** (generate + verify + fix) — CLAUDE.md にはプロジェクト固有の3-5ファイルのみ（~8Kトークン）。全ルールは `/ai-dev-os-check` で事後検証。[ベンチマークデータ](https://github.com/yunbow/ai-dev-os-benchmark)でこのアプローチは 96.9/100 を記録。10ファイル以上のロードはガイドラインなしより低スコア。

## 対応ツール

AI Dev OS は、主要な AI コーディングアシスタントの効果的なルールファイルを体系的に作成するアプローチを提供します:

- **Claude Code** — `CLAUDE.md` とカスタムスキル経由（[プラグイン](https://github.com/yunbow/ai-dev-os-plugin-claude-code)）
- **Kiro** — `AGENTS.md` とステアリングルール経由（[プラグイン](https://github.com/yunbow/ai-dev-os-plugin-kiro)）
- **Cursor** — `.cursorrules` と `.mdc` ファイル経由（[プラグイン](https://github.com/yunbow/ai-dev-os-plugin-cursor)）

## エコシステム

| リポジトリ | 説明 |
|---|---|
| **ai-dev-os**（本リポジトリ） | フレームワーク仕様と理論 |
| [rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript / Next.js / Node.js ガイドライン |
| [rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python / FastAPI ガイドライン |
| [plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Claude Code 向け Skills / Hooks / Agents |
| [plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Kiro 向け Steering Rules / Hooks |
| [plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Cursor Rules (.mdc) |
| [cli](https://github.com/yunbow/ai-dev-os-cli) | `npx ai-dev-os init` |
| [benchmark](https://github.com/yunbow/ai-dev-os-benchmark) | 定量ベンチマーク — ガイドラインの品質影響データ |

## さらに詳しく

- [4層モデル](spec/4-layer-model.md) | [依存性ルール](spec/dependency-rule.md) | [Specificity Cascade](spec/priority-cascade.md) | [賞味期限モデル](spec/shelf-life.md)
- [Tacit-to-Explicit Engineering](theory/tacit-to-explicit.md) | [古典理論との対応](theory/classical-theories.md) | [将来性](theory/future-proofing.md)
- [フレームワーク比較](getting-started/comparison.md) | [ガイドライン vs マルチエージェント](getting-started/guideline-vs-multi-agent.md) | [ツール移行ガイド](getting-started/migration.md)
- [Zenn Book: AI DEV OS](https://zenn.dev/yun_bow)

<details>
<summary>ディレクトリ構造</summary>

```text
ai-dev-os/
├── spec/                        # フレームワーク仕様
│   ├── 4-layer-model.md         #   Lifespan Layers（4層モデル）
│   ├── dependency-rule.md       #   依存性ルール
│   ├── priority-cascade.md      #   Specificity Cascade
│   ├── shelf-life.md            #   賞味期限モデル
│   └── governance.md            #   ガバナンスモデル
├── theory/                      # 理論的背景
├── getting-started/             # 導入ガイド
└── docs/                        # 運用ガイド・多言語版
```

> 実際のガイドラインファイル（01_philosophy/ ... 04_ai-prompts/）は
> [ルールリポジトリ](https://github.com/yunbow/ai-dev-os-rules-typescript)にあり、本リポジトリには含まれません。

</details>

## ライセンス

[MIT](../../../LICENSE)

---

Languages: [English](../../../README.md) | 日本語 | [简体中文](../zh-CN/README.md) | [한국어](../ko/README.md) | [Español](../es/README.md)

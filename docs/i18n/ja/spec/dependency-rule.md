# AI コーディングルールの依存性ルール

## 原則

> 上位層は下位層を参照してはならない。

これは Robert C. Martin の Clean Architecture の依存性ルールおよび Christopher Alexander のパターンランゲージ階層から直接借用したものです。

## 層ごとのルール

### L1: Philosophy
- 含めてはならないもの: ツール名、フレームワーク名、ライブラリ名、API名
- 含めてはならないもの: 特定言語のコード例
- 含めてよいもの: 抽象的な概念、価値観、思考フレームワーク

### L2: Decision Criteria
- 含めてはならないもの: フレームワーク固有の実装詳細
- 含めてはならないもの: 特定のライブラリAPI参照
- 含めてよいもの: 言語パラダイム（OOP、FP）、一般的なパターン（MVC、CQRS）

### L3: Guidelines
- 含めてはならないもの: ツール固有の設定（CLAUDE.md の形式、.cursorrules の構文）
- 含めてよいもの: フレームワーク名、ライブラリ名、コード例

### L4: AI Frames
- 含めてよいもの: ツール固有のあらゆるもの
- 参照すべきもの: 情報源としての L3 ガイドライン

## 違反検出

`/ai-dev-os-audit` コマンドは以下をスキャンして依存性違反をチェックします。
- L1 ファイル内のツール/フレームワーク用語
- L2 ファイル内の実装詳細

プラグインフックにより、L1〜L2 ファイルの編集時にリアルタイムで警告も提供されます。

---

Languages: [English](../../../../spec/dependency-rule.md) | 日本語 | [简体中文](../../zh-CN/spec/dependency-rule.md) | [한국어](../../ko/spec/dependency-rule.md) | [Español](../../es/spec/dependency-rule.md)

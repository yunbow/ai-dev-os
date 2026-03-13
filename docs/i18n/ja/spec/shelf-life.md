# AI コーディングルールの Shelf-Life モデル

## コンセプト

各層には「Shelf Life（有効期間）」があり、内容の大幅な改訂が必要になるまでの想定期間を表します。

| 層 | Shelf Life | アナロジー |
|-------|-----------|---------|
| L1: Philosophy | 2〜5年 | 都市の道路配置 |
| L2: Decision Criteria | 1〜3年 | 建物の建築設計 |
| L3: Guidelines | 6〜12ヶ月 | インテリアデザイン |
| L4: AI Frames | 2〜4ヶ月 | 家具の配置 |

## 投資戦略

上位層に最も重点的に投資すべきです。なぜなら、上位のエラーは下位に波及するからです。

- **L1 のエラー**（誤った哲学）→ 壊滅的、ほぼ見えない、すべてに影響する
- **L2 のエラー**（誤った原則）→ 高コスト、検出が困難、すべてのコードに影響する
- **L3 のエラー**（誤ったガイドライン）→ 中程度、レビューで検出可能、特定のパターンに影響する
- **L4 のエラー**（誤ったツール設定）→ 低コスト、即座に可視化、容易に修正可能

## 期限切れの検出

`git log` を使って陳腐化を検出します。

```bash
# Check last update date for each layer
git log -1 --format="%ci" -- 01_philosophy/
git log -1 --format="%ci" -- 02_decision-criteria/
git log -1 --format="%ci" -- 03_guidelines/
git log -1 --format="%ci" -- 04_ai-frames/
```

`/ai-dev-os-audit` コマンドがこのチェックを自動化します。

---

Languages: [English](../../../../spec/shelf-life.md) | 日本語 | [简体中文](../../zh-CN/spec/shelf-life.md) | [한국어](../../ko/spec/shelf-life.md) | [Español](../../es/spec/shelf-life.md)

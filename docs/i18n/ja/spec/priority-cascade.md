# Specificity Cascade — AI Coding Rules

## CSS詳細度のアナロジー

AI Dev OS は CSS の詳細度にヒントを得た Specificity Cascade を使ってルールの競合を解決します。

```
1. [Highest] frameworks/[stack]/*   ← Most specific
2. [High]    common/*               ← Common but concrete
3. [Medium]  project-specific/*     ← Project context
4. [Low]     02_decision-criteria/* ← Abstract criteria
5. [Lowest]  01_philosophy/*        ← Most abstract
```

> **注**: `project-specific/*` はユーザーのプロジェクト内のガイドライン（例: `docs/guidelines/billing.md`）を指し、rules リポジトリ内のものではありません。rules リポジトリには `frameworks/` と `common/` のみが含まれます。プロジェクト固有のガイドラインは、ドメインロジック、外部連携、法的要件などに対してユーザーが作成するものです。

## 仕組み

1. コーディング時、AIはまず**フレームワーク固有**のルール（最も具体的）を探す
2. フレームワークルールがなければ、**共通**ルールにフォールバックする
3. 共通ルールもなければ、**プロジェクト固有**の規約にフォールバックする
4. 明示的なルールがなければ、**Decision Criteria** を適用して最善のアプローチを推論する
5. 最終手段として、**Philosophy** に基づく価値判断にフォールバックする

## 例: エラーハンドリング

AIが Next.js の Server Action でエラーハンドリングの判断に直面したとします。

1. **frameworks/nextjs/server-actions.md** に「ActionResult<T> パターンを使用する」とある → **これを適用する**
2. **common/error-handling.md** に「エラーをユーザー/システム/バリデーションに分類する」とある → これも適用する
3. **02_decision-criteria/error-strategy.md** に「例外よりも明示的なエラー型を優先する」とある → アプローチの参考になる
4. **01_philosophy/principles.md** に「利便性より正確性」とある → 根底にある価値観

すべての層が寄与しますが、競合がある場合は最も具体的なルールが優先されます。

---

Languages: [English](../../../../spec/priority-cascade.md) | 日本語 | [简体中文](../../zh-CN/spec/priority-cascade.md) | [한국어](../../ko/spec/priority-cascade.md) | [Español](../../es/spec/priority-cascade.md)

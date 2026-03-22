# ルールの選び方

## 利用可能なルールセット

| リポジトリ | 言語 | フレームワーク |
|---|---|---|
| [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript | Next.js (App Router), Node.js CLI |
| [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python | FastAPI, Flask, Typer CLI |

## ルールセットの中身

各ルールセットには、完全な4層構造が含まれています:

```text
ai-dev-os-rules-{language}/
├── 01_philosophy/               # L1: 設計思想（サンプル、自分の言葉で書き換え）
├── 02_decision-criteria/        # L2: 判断基準（サンプル、自分の言葉で書き換え）
├── 03_guidelines/               # L3: ガイドライン
│   ├── common/                  #   言語非依存のルール（13ファイル）
│   └── frameworks/              #   フレームワーク固有のルール
├── 04_ai-prompts/               # L4: AIプロンプト＆スキル
└── templates/                   # プロジェクトスキャフォールディングテンプレート
```

## 対応する言語がない場合

1. [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) をフォークして出発点にする
2. `01_philosophy/`、`02_decision-criteria/`、`03_guidelines/common/` はそのまま残す（これらは言語非依存）
3. `03_guidelines/frameworks/` を自分のフレームワークのガイドラインに置き換える
4. `04_ai-prompts/` と `templates/` を自分の技術スタックに合わせて更新する

---

Languages: [English](../../../../getting-started/choose-rules.md) | 日本語 | [简体中文](../../zh-CN/getting-started/choose-rules.md) | [한국어](../../ko/getting-started/choose-rules.md) | [Español](../../es/getting-started/choose-rules.md)

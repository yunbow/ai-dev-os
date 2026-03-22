# AI Dev OS — 運用ガイド

このドキュメントは、**ai-dev-os コアリポジトリ**（仕様、理論、導入ガイド）の運用について説明します。

個別コンポーネントの運用ガイドについては以下を参照してください:

- **ルール**: 各ルールリポジトリの `docs/operation-guide.md`
- **プラグイン**: 各プラグインリポジトリの `docs/operation-guide.md`

---

## 1. リポジトリ構成

```text
ai-dev-os/
├── spec/                        # フレームワーク仕様
├── theory/                      # 理論的背景
├── getting-started/             # 導入ガイド
└── docs/                        # 本ガイド + 多言語版
```

このリポジトリには、AI Dev OS フレームワークの**仕様と理論のみ**が含まれます。実際のガイドラインファイルはルールリポジトリにあります:

- [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript)
- [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python)

---

## 2. 更新ポリシー

### 2.1 更新タイミング

| セクション | 更新トリガー | 頻度 |
|---------|---------------|-----------|
| `spec/` | 4層モデルの設計変更、新しい設計原則 | 非常にまれ |
| `theory/` | 新しい理論的関連の発見、研究参照の更新 | まれ |
| `getting-started/` | 新しいルール/プラグインの追加、エコシステムの変更 | 中程度 |
| `docs/` | ガイドの改善、新しい多言語翻訳 | 中程度 |

### 2.2 更新ルール

- **spec/**: ここの変更はエコシステム全体に影響します。MAJOR バージョン変更として扱ってください。
- **theory/**: 学術的参考文献と理論分析です。事実に基づき、適切に引用してください。
- **getting-started/**: 最新のルール/プラグインリポジトリと同期を保つ必要があります。
- 新しいルールリポジトリやプラグインを追加する場合、以下を更新してください:
  - `README.md`（エコシステムテーブル、はじめにセクション）
  - `getting-started/choose-rules.md` または `getting-started/choose-plugin.md`

---

## 3. バージョニング

セマンティックバージョニング（git タグ）で管理します。

| 変更の種類 | バージョン | 例 |
|-------------|---------|--------|
| 基本仕様の変更（4層モデルの再設計） | MAJOR | v2.0.0 |
| 新しい理論ドキュメント、導入ガイドの更新 | MINOR | v1.1.0 |
| 誤字修正、表現の改善 | PATCH | v1.0.1 |

---

## 4. 言語ポリシー

- このリポジトリのすべてのコンテンツは**英語**で記述されています
- 多言語版の運用ガイドは `docs/i18n/` で管理されています（JA, ZH-CN, KO, ES）
- README.md の多言語翻訳は `docs/i18n/{lang}/README.md` にあります

---

Languages: [English](../../operation-guide.md) | 日本語 | [简体中文](../zh-CN/operation-guide.md) | [한국어](../ko/operation-guide.md) | [Español](../es/operation-guide.md)

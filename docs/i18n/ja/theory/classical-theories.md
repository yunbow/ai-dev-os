# 古典的ソフトウェアエンジニアリング理論

## 概要

AI Dev OSの4層モデルは新しい発明ではない――50年にわたる15の確立されたソフトウェアエンジニアリング理論で観察されたパターンに対応している。

## Tier 1: 直接的な構造的類似性

### Clean Architecture (Robert C. Martin, 2012/2017)

| AI Dev OS | Clean Architecture | 安定性 |
|-----------|-------------------|-----------|
| L1: Philosophy | Entities (Business Rules) | 最高 |
| L2: Decision Criteria | Use Cases (Application Rules) | 高 |
| L3: Guidelines | Interface Adapters | 中 |
| L4: AI Frames | Frameworks & Drivers | 最低 |

**重要な洞察**: 依存性のルール――ソースコードの依存関係は内側に向かわなければならない。

### Pattern Languages (Christopher Alexander, 1977)

| AI Dev OS | Pattern Language | スケール |
|-----------|----------------|-------|
| L1: Philosophy | "Quality Without a Name" | 都市 |
| L2: Decision Criteria | 大規模パターン | 地区 |
| L3: Guidelines | 中規模パターン | 建物 |
| L4: AI Frames | 小規模パターン | 素材 |

**重要な洞察**: 大きなパターンほど長く生き残る。抽象的なパターンが具体的なパターンを生成する。

### SECI Model (Nonaka & Takeuchi, 1995)

| AI Dev OS | SECI | 知識の流れ |
|-----------|------|----------------|
| L1: Philosophy | Socialization（共同化） | 暗黙知 → 暗黙知 |
| L2: Decision Criteria | Externalization（表出化） | 暗黙知 → 形式知 |
| L3: Guidelines | Combination（連結化） | 形式知 → 形式知 |
| L4: AI Frames | Internalization（内面化） | 形式知 → 暗黙知 |

**重要な洞察**: 知識創造は線形ではなくスパイラル（螺旋）である。実践がフィロソフィーにフィードバックされる。

### Agile Manifesto (2001)

| AI Dev OS | Agile | 変化の速度 |
|-----------|-------|-------------|
| L1: Philosophy | 4つの核心的価値 | ほぼ不変 |
| L2: Decision Criteria | 12の原則 | 低 |
| L3: Guidelines | Scrum/XP/Kanbanのプラクティス | 中 |
| L4: AI Frames | Jira Workflows, CI/CD Config | 高 |

**重要な洞察**: カーゴカルトへの警告――L1-L2を理解せずにL3-L4をコピーすると失敗する。

## Tier 2: 部分的な構造的類似性

| 理論 | AI Dev OSへの主要な貢献 |
|--------|-------------------------------|
| **Domain-Driven Design** (Evans, 2003) | Bounded Context → ドメインごとにスコープされたガイドライン |
| **Zachman Framework** (1987) | 各レイヤーは単に詳細度が異なるのではなく、質的に異なる |
| **Software Product Lines** (CMU SEI, 2001) | コア資産と製品固有資産；バリエーションポイント |
| **TOGAF** (The Open Group, 1995) | ガバナンス：誰がどのレイヤーを変更できるか |
| **Architecture Decision Records** (Nygard, 2011) | 決定だけでなく根拠を記録する；置換の追跡 |
| **GoF Design Patterns** (1994) | 30年の実証：抽象パターンは具体パターンより長生きする |

## 6つの横断的法則

15の理論すべてを分析すると、6つの普遍的法則が明らかになる：

| # | 法則 | 根拠となる理論 |
|---|-----|-----------------|
| 1 | **依存性のルール** ― 上位レイヤーは下位レイヤーを参照してはならない | Clean Architecture, Pattern Languages |
| 2 | **寿命 = 抽象度** ― 抽象的なものほど長く生き残る | Clean Architecture, GoF, Alexander, Zachman |
| 3 | **レイヤースキップの禁止** ― 成熟は段階的でなければならない | CMMI, Agile（カーゴカルト）, Craftsmanship |
| 4 | **質的差異** ― レイヤーは程度ではなく種類が異なる | Zachman, ISO 42010, Kruchten |
| 5 | **スパイラルフィードバック** ― 実践はフィロソフィーにフィードバックされなければならない | SECI, Alexander |
| 6 | **トレーサビリティ = 生成力** ― レイヤー間の明示的なリンクが、新規状況での推論を可能にする | Pattern Languages, ADR, GoF |

## 参考文献

- Alexander, C. (1977). *A Pattern Language*. Oxford University Press.
- Beck, K. et al. (2001). "Manifesto for Agile Software Development."
- Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.
- Gamma, E. et al. (1994). *Design Patterns*. Addison-Wesley.
- Martin, R.C. (2017). *Clean Architecture*. Prentice Hall.
- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Zachman, J. (1987). "A Framework for Information Systems Architecture." *IBM Systems Journal*, 26(3).

---

Languages: [English](../../../../theory/classical-theories.md) | 日本語 | [简体中文](../../zh-CN/theory/classical-theories.md) | [한국어](../../ko/theory/classical-theories.md) | [Español](../../es/theory/classical-theories.md)

# Tacit-to-Explicit Engineering（暗黙知→形式知エンジニアリング）

## 核心的な問題

> AIが生成するコードは「ほぼ正しいが微妙に間違っている」――開発者の66%がこれを最大の不満として挙げている。

根本原因は、プロンプトの不足やAIモデルの性能不足ではない。**シニア開発者の暗黙知が、明示的で強制可能なルールに変換されていない**ことにある。

## 暗黙知とは何か？

暗黙知（Tacit Knowledge）とは、言語化が困難な知識のことである：

- 「このコードはなんか違う」→ 具体的にどのルールに違反しているのか？
- 「うちではそういうやり方はしない」→ 「そういうやり方」はどこに文書化されているのか？
- 「シニアエンジニアなら誰でも知っている」→ しかしAIはシニアエンジニアではない

## SECI Modelとの関係

AI Dev OSは、野中郁次郎（Ikujiro Nonaka）のSECI Model（知識創造モデル、1995年）に直接対応している：

| SECIフェーズ | AI Dev OSレイヤー | 知識の流れ |
|-----------|----------------|----------------|
| Socialization（共同化） | L1: Philosophy | 暗黙知 → 暗黙知：経験を通じた共有 |
| Externalization（表出化） | L2: Decision Criteria | 暗黙知 → 形式知：原則として言語化 |
| Combination（連結化） | L3: Guidelines | 形式知 → 形式知：ルールとして体系化 |
| Internalization（内面化） | L4: AI Frames | 形式知 → 暗黙知：実践を通じた体得 |

重要な洞察：**AI Dev OSは単なるドキュメント階層ではなく、知識創造システムである。**

## スパイラル

SECI Modelは一方向のプロセスではなく、スパイラル（螺旋）である：

```text
L4 practice → discovers new tacit knowledge → L1 evolves
     ↑                                              ↓
     └──── L3 rules ← L2 principles ← L1 values ──┘
```

`/ai-dev-os-evolve` コマンドは、直近のコーディング実践を分析し、L1-L2への更新を提案することで、このスパイラルを実装している。

## なぜこれが重要なのか

明示的なルールがない場合：

- AIは**見た目は正しいがチームの規範に違反するコード**を生成する
- コードレビューが同じ問題に対する**繰り返しの指導セッション**になる
- 人が離れると**知識も失われる**――AIはそれを学ぶ機会がなかった

AI Dev OSがある場合：

- 暗黙知が明示的でバージョン管理され、強制可能なルールとして捕捉される
- AIは**コードレビューのたびに改善される**（Rule Harvestingを通じて）
- 知識は**チームの変動やツールの移行を超えて存続する**

## 参考文献

- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Nonaka, I. & Konno, N. (1998). "The Concept of 'Ba'." *California Management Review*, 40(3).

---

Languages: [English](../../../../theory/tacit-to-explicit.md) | 日本語 | [简体中文](../../zh-CN/theory/tacit-to-explicit.md) | [한국어](../../ko/theory/tacit-to-explicit.md) | [Español](../../es/theory/tacit-to-explicit.md)

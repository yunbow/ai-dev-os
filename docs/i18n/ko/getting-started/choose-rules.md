# 규칙 선택하기

## 사용 가능한 규칙 세트

| 리포지토리 | 언어 | 프레임워크 |
|------------|------|-----------|
| [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | TypeScript | Next.js (App Router), Node.js CLI |
| [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | Python | FastAPI, Flask, Typer CLI |

## 규칙 세트에 포함된 내용

각 규칙 세트에는 전체 4계층 구조가 포함되어 있습니다:

```
ai-dev-os-rules-{language}/
├── 01_philosophy/               # L1: 설계 철학 (샘플, 여러분의 언어로 재작성)
├── 02_decision-criteria/        # L2: 판단 기준 (샘플, 여러분의 언어로 재작성)
├── 03_guidelines/               # L3: 가이드라인
│   ├── common/                  #   언어 독립적 규칙 (13개 파일)
│   └── frameworks/              #   프레임워크별 규칙
├── 04_ai-prompts/               # L4: AI 프롬프트 & 스킬
└── templates/                   # 프로젝트 스캐폴딩 템플릿
```

## 지원되지 않는 언어를 사용하는 경우

1. [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript)를 시작점으로 포크합니다
2. `01_philosophy/`, `02_decision-criteria/`, `03_guidelines/common/`은 유지합니다 (언어 독립적)
3. `03_guidelines/frameworks/`를 여러분의 프레임워크 가이드라인으로 교체합니다
4. `04_ai-prompts/`와 `templates/`를 여러분의 스택에 맞게 업데이트합니다

---

Languages: [English](../../../../getting-started/choose-rules.md) | [日本語](../../ja/getting-started/choose-rules.md) | [简体中文](../../zh-CN/getting-started/choose-rules.md) | 한국어 | [Español](../../es/getting-started/choose-rules.md)

# Tacit-to-Explicit Engineering（암묵지→형식지 공학）

## 핵심 문제

> AI가 생성한 코드는 "거의 맞지만 미묘하게 틀리다" — 개발자의 66%가 이를 가장 큰 불만으로 꼽습니다.

근본 원인은 불충분한 프롬프팅이나 열악한 AI 모델이 아닙니다. **시니어 개발자의 암묵적 지식이 명시적이고 강제 가능한 규칙으로 변환되지 않았기** 때문입니다.

## 암묵지란?

암묵지(暗黙知)는 명문화하기 어려운 지식입니다:

- "이 코드는 뭔가 느낌이 이상하다" → 어떤 구체적인 규칙이 위반되고 있는가?
- "우리는 여기서 그렇게 하지 않는다" → "그렇게"는 어디에 문서화되어 있는가?
- "시니어 엔지니어라면 누구나 이걸 알 것이다" → 하지만 AI는 시니어 엔지니어가 아니다

## SECI 모델과의 연결

AI Dev OS는 노나카 이쿠지로의 SECI 지식 창조 모델(1995)에 직접 대응됩니다:

| SECI 단계 | AI Dev OS 계층 | 지식 흐름 |
|-----------|---------------|-----------|
| 공동화 (Socialization) | L1: 철학 | 암묵지 → 암묵지: 경험을 통해 공유 |
| 표출화 (Externalization) | L2: 판단 기준 | 암묵지 → 형식지: 원칙으로 명문화 |
| 연결화 (Combination) | L3: 가이드라인 | 형식지 → 형식지: 규칙으로 체계화 |
| 내면화 (Internalization) | L4: AI 프레임 | 형식지 → 암묵지: 실천을 통해 체화 |

핵심 통찰: **AI Dev OS는 단순한 문서 계층 구조가 아닌 지식 창조 시스템입니다.**

## 나선형 구조

SECI 모델은 일방향 프로세스가 아닌 나선형입니다:

```text
L4 실천 → 새로운 암묵지 발견 → L1 진화
     ↑                                ↓
     └──── L3 규칙 ← L2 원칙 ← L1 가치 ──┘
```

`/ai-dev-os-evolve` 명령은 최근 코딩 실천을 분석하고 L1-L2에 대한 업데이트를 제안하여 이 나선형을 구현합니다.

## 왜 중요한가

명시적 규칙이 없으면:

- AI가 **올바르게 보이지만 팀 규범을 위반하는** 코드를 생성합니다
- 코드 리뷰가 동일한 이슈에 대한 **반복적인 교육 세션**이 됩니다
- 사람이 떠날 때 **지식도 떠납니다** — AI는 그것을 배우지 못했습니다

AI Dev OS를 사용하면:

- 암묵지가 명시적이고, 버전 관리되며, 강제 가능한 규칙으로 포착됩니다
- AI가 **모든 코드 리뷰를 통해 향상됩니다** (Rule Harvesting을 통해)
- 지식이 **팀 변경과 도구 마이그레이션에서도 살아남습니다**

## 참고문헌

- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Nonaka, I. & Konno, N. (1998). "The Concept of 'Ba'." *California Management Review*, 40(3).

---

Languages: [English](../../../../theory/tacit-to-explicit.md) | [日本語](../../ja/theory/tacit-to-explicit.md) | [简体中文](../../zh-CN/theory/tacit-to-explicit.md) | 한국어 | [Español](../../es/theory/tacit-to-explicit.md)

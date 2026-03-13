# 고전 소프트웨어 공학 이론

## 개요

AI Dev OS의 4계층 모델은 새로운 발명이 아닙니다 — 50년에 걸친 15개 확립된 소프트웨어 공학 이론에서 관찰된 패턴에 대응됩니다.

## Tier 1: 직접적 구조 유사성

### Clean Architecture (Robert C. Martin, 2012/2017)

| AI Dev OS | Clean Architecture | 안정성 |
|-----------|-------------------|--------|
| L1: 철학 | 엔티티 (비즈니스 규칙) | 최고 |
| L2: 판단 기준 | 유스케이스 (애플리케이션 규칙) | 높음 |
| L3: 가이드라인 | 인터페이스 어댑터 | 중간 |
| L4: AI 프레임 | 프레임워크 & 드라이버 | 최저 |

**핵심 통찰**: 의존성 규칙 — 소스 코드 의존성은 반드시 안쪽을 향해야 합니다.

### Pattern Languages (Christopher Alexander, 1977)

| AI Dev OS | Pattern Language | 규모 |
|-----------|----------------|------|
| L1: 철학 | "이름 없는 질" | 도시 |
| L2: 판단 기준 | 대규모 패턴 | 지구 |
| L3: 가이드라인 | 중규모 패턴 | 건물 |
| L4: AI 프레임 | 소규모 패턴 | 재료 |

**핵심 통찰**: 더 큰 패턴이 더 오래 살아남습니다. 추상적 패턴이 구체적 패턴을 생성합니다.

### SECI 모델 (Nonaka & Takeuchi, 1995)

| AI Dev OS | SECI | 지식 흐름 |
|-----------|------|-----------|
| L1: 철학 | 공동화 | 암묵지 → 암묵지 |
| L2: 판단 기준 | 표출화 | 암묵지 → 형식지 |
| L3: 가이드라인 | 연결화 | 형식지 → 형식지 |
| L4: AI 프레임 | 내면화 | 형식지 → 암묵지 |

**핵심 통찰**: 지식 창조는 선형이 아닌 나선형입니다. 실천이 철학에 피드백됩니다.

### Agile Manifesto (2001)

| AI Dev OS | Agile | 변화율 |
|-----------|-------|--------|
| L1: 철학 | 4가지 핵심 가치 | 거의 불변 |
| L2: 판단 기준 | 12가지 원칙 | 낮음 |
| L3: 가이드라인 | Scrum/XP/Kanban 실천 | 중간 |
| L4: AI 프레임 | Jira 워크플로, CI/CD 설정 | 높음 |

**핵심 통찰**: 카고 컬트 경고 — L1-L2를 이해하지 않고 L3-L4를 복사하면 실패합니다.

## Tier 2: 부분적 구조 유사성

| 이론 | AI Dev OS에 대한 핵심 기여 |
|------|---------------------------|
| **Domain-Driven Design** (Evans, 2003) | Bounded Context → 도메인별 범위 지정 가이드라인 |
| **Zachman Framework** (1987) | 각 계층은 단순히 더 상세한 것이 아니라 질적으로 다름 |
| **Software Product Lines** (CMU SEI, 2001) | 코어 자산 vs 제품별 자산; 변동점 |
| **TOGAF** (The Open Group, 1995) | 거버넌스: 누가 어떤 계층을 변경할 수 있는가 |
| **Architecture Decision Records** (Nygard, 2011) | 결정뿐 아니라 근거를 기록; 대체 추적 |
| **GoF Design Patterns** (1994) | 30년간의 증거: 추상적 패턴이 구체적 패턴보다 오래 살아남음 |

## 6가지 교차 법칙

15개 이론 전체를 분석하면 6가지 보편적 법칙이 드러납니다:

| # | 법칙 | 출처 이론 |
|---|------|-----------|
| 1 | **의존성 규칙** — 상위 계층은 하위 계층을 참조해서는 안 됩니다 | Clean Architecture, Pattern Languages |
| 2 | **수명 = 추상도** — 추상적인 것이 더 오래 살아남습니다 | Clean Architecture, GoF, Alexander, Zachman |
| 3 | **계층 건너뛰기 금지** — 성숙도는 순차적입니다 | CMMI, Agile (카고 컬트), Craftsmanship |
| 4 | **질적 차이** — 계층은 정도가 아닌 종류가 다릅니다 | Zachman, ISO 42010, Kruchten |
| 5 | **나선형 피드백** — 실천은 반드시 철학에 피드백되어야 합니다 | SECI, Alexander |
| 6 | **추적 가능성 = 생성성** — 계층 간 명시적 연결이 새로운 상황에서의 추론을 가능하게 합니다 | Pattern Languages, ADR, GoF |

## 참고문헌

- Alexander, C. (1977). *A Pattern Language*. Oxford University Press.
- Beck, K. et al. (2001). "Manifesto for Agile Software Development."
- Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.
- Gamma, E. et al. (1994). *Design Patterns*. Addison-Wesley.
- Martin, R.C. (2017). *Clean Architecture*. Prentice Hall.
- Nonaka, I. & Takeuchi, H. (1995). *The Knowledge-Creating Company*. Oxford University Press.
- Zachman, J. (1987). "A Framework for Information Systems Architecture." *IBM Systems Journal*, 26(3).

---

Languages: [English](../../../../theory/classical-theories.md) | [日本語](../../ja/theory/classical-theories.md) | [简体中文](../../zh-CN/theory/classical-theories.md) | 한국어 | [Español](../../es/theory/classical-theories.md)

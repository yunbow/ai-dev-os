# Specificity Cascade — AI Coding Rules

## CSS 특이성 비유

AI Dev OS는 CSS 특이성에서 영감을 받은 우선순위 캐스케이드를 사용하여 규칙 충돌을 해결합니다:

```
1. [최고]   frameworks/[stack]/*   ← 가장 구체적
2. [높음]   common/*               ← 공통이지만 구체적
3. [중간]   project-specific/*     ← 프로젝트 컨텍스트
4. [낮음]   02_decision-criteria/* ← 추상적 기준
5. [최저]   01_philosophy/*        ← 가장 추상적
```

> **참고**: `project-specific/*`는 규칙 리포지토리가 아닌 사용자 프로젝트의 가이드라인(예: `docs/guidelines/billing.md`)을 의미합니다. 규칙 리포지토리에는 `frameworks/`와 `common/`만 포함됩니다. 프로젝트별 가이드라인은 도메인 로직, 외부 연동, 법적 요구사항 등을 위해 사용자가 작성합니다.

## 작동 방식

1. 코딩 시, AI는 먼저 **프레임워크별** 규칙을 찾습니다 (가장 구체적)
2. 프레임워크 규칙이 없으면 **공통** 규칙으로 대체합니다
3. 공통 규칙이 없으면 **프로젝트별** 관례로 대체합니다
4. 명시적인 것이 없으면 **판단 기준**을 적용하여 최선의 접근법을 추론합니다
5. 최후의 수단으로 **철학**에 기반한 가치 판단으로 대체합니다

## 예제: 에러 처리

AI가 Next.js Server Action에서 에러 처리 결정을 만나는 경우를 가정합니다:

1. **frameworks/nextjs/server-actions.md**에 "ActionResult<T> 패턴 사용" → **이것을 적용**
2. **common/error-handling.md**에 "에러를 사용자/시스템/유효성 검사로 분류" → 함께 적용
3. **02_decision-criteria/error-strategy.md**에 "예외보다 명시적 에러 타입 선호" → 접근법에 참고
4. **01_philosophy/principles.md**에 "편의보다 정확성" → 기저 가치

모든 계층이 기여하지만, 충돌이 있을 때는 가장 구체적인 규칙이 우선합니다.

---

Languages: [English](../../../../spec/priority-cascade.md) | [日本語](../../ja/spec/priority-cascade.md) | [简体中文](../../zh-CN/spec/priority-cascade.md) | 한국어 | [Español](../../es/spec/priority-cascade.md)

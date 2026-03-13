# 플러그인 선택하기

## 사용 가능한 플러그인

| 도구 | 리포지토리 | 기능 |
|------|-----------|------|
| [Claude Code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | Skills (슬래시 커맨드), Hooks, Sub-agents | 라이프사이클 훅을 통한 완전 자동화 |
| [Kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | Steering Rules, Hooks | 자동/수동/fileMatch 활성화 모드 |
| [Cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | Rules (.mdc) | 파일 스코프 및 에이전트 요청 규칙 |

## 기능 비교

| 기능 | Claude Code | Kiro | Cursor |
|------|------------|------|--------|
| 설정 마법사 | `/ai-dev-os-init` | `#ai-dev-os-init` | `@ai-dev-os-init` |
| 차분 검사 | `/ai-dev-os-check` | `#ai-dev-os-check` | `@ai-dev-os-check` |
| 전체 스캔 | `/ai-dev-os-scan` | `#ai-dev-os-scan` | `@ai-dev-os-scan` |
| 규칙 추출 | `/ai-dev-os-extract` | `#ai-dev-os-extract` | `@ai-dev-os-extract` |
| 구현 계획 | `/ai-dev-os-plan` | `#ai-dev-os-plan` | `@ai-dev-os-plan` |
| 규칙 설명 | `/ai-dev-os-why` | `#ai-dev-os-why` | `@ai-dev-os-why` |
| 상태 감사 | `/ai-dev-os-audit` | `#ai-dev-os-audit` | `@ai-dev-os-audit` |
| SECI 진화 | `/ai-dev-os-evolve` | `#ai-dev-os-evolve` | `@ai-dev-os-evolve` |
| 준수 보고서 | `/ai-dev-os-report` | `#ai-dev-os-report` | `@ai-dev-os-report` |
| 티켓 생성 | `/ai-dev-os-ticket` | `#ai-dev-os-ticket` | `@ai-dev-os-ticket` |
| Pre-commit 훅 | ✅ | ✅ | — |
| 파일 저장 훅 | — | ✅ | — |
| 자동 코드 검사 | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| L1-L2 의존성 경고 | ✅ (Hook) | ✅ (fileMatch) | ✅ (globs) |
| Sub-agents | ✅ (3개 에이전트) | — | — |

## 목록에 없는 도구를 사용하는 경우

4계층 가이드라인(L1-L3)은 어떤 AI 코딩 도구에서도 작동합니다. L4(AI 프레임)만 도구별입니다. 다음과 같이 할 수 있습니다:

1. 규칙 리포지토리를 직접 사용하고 도구의 설정 파일에서 가이드라인을 참조
2. 플러그인 리포지토리를 참고하여 자체 통합을 생성

---

Languages: [English](../../../../getting-started/choose-plugin.md) | [日本語](../../ja/getting-started/choose-plugin.md) | [简体中文](../../zh-CN/getting-started/choose-plugin.md) | 한국어 | [Español](../../es/getting-started/choose-plugin.md)

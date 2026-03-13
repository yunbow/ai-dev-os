# AI Dev OS — 운영 가이드

English | [日本語](../ja/operation-guide.md) | [简体中文](../zh-CN/operation-guide.md) | 한국어 | [Español](../es/operation-guide.md)

이 문서는 **ai-dev-os 코어 리포지토리**(명세, 이론, 시작하기 가이드)의 운영에 대해 다룹니다.

특정 구성요소의 운영 가이드는 아래를 참조하세요:
- **규칙**: 각 규칙 리포지토리에 자체 `docs/operation-guide.md`가 있습니다
- **플러그인**: 각 플러그인 리포지토리에 자체 `docs/operation-guide.md`가 있습니다

---

## 1. 리포지토리 구조

```
ai-dev-os/
├── spec/                        # 프레임워크 명세
├── theory/                      # 이론적 배경
├── getting-started/             # 시작하기 가이드
└── docs/                        # 이 가이드 + 다국어
```

이 리포지토리에는 AI Dev OS 프레임워크의 **명세와 이론만** 포함되어 있습니다. 실제 가이드라인 파일은 규칙 리포지토리에 있습니다:
- [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript)
- [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python)

---

## 2. 업데이트 정책

### 2.1 업데이트 시점

| 섹션 | 업데이트 트리거 | 빈도 |
|------|----------------|------|
| `spec/` | 4계층 모델 설계 변경, 새로운 설계 원칙 | 매우 드묾 |
| `theory/` | 새로운 이론적 연결, 연구 참고문헌 업데이트 | 드묾 |
| `getting-started/` | 새로운 규칙/플러그인 추가, 에코시스템 변경 | 보통 |
| `docs/` | 가이드 개선, 새로운 다국어 번역 | 보통 |

### 2.2 업데이트 규칙

- **spec/**: 여기서의 변경은 전체 에코시스템에 영향을 미칩니다. MAJOR 버전 변경으로 취급하세요.
- **theory/**: 학술 참고문헌 및 이론적 분석. 사실에 기반하고 충분한 인용을 유지하세요.
- **getting-started/**: 최신 규칙/플러그인 리포지토리와 동기화를 유지해야 합니다.
- 새로운 규칙 리포지토리나 플러그인을 추가할 때 업데이트할 항목:
  - `README.md` (에코시스템 표, 시작하기 섹션)
  - `getting-started/choose-rules.md` 또는 `getting-started/choose-plugin.md`

---

## 3. 버전 관리

시맨틱 버전 관리(git 태그)로 관리됩니다.

| 변경 유형 | 버전 | 예시 |
|-----------|------|------|
| 기본 명세 변경 (4계층 모델 재설계) | MAJOR | v2.0.0 |
| 새로운 이론 문서, 시작하기 업데이트 | MINOR | v1.1.0 |
| 오탈자 수정, 문구 개선 | PATCH | v1.0.1 |

---

## 4. 언어 정책

- 이 리포지토리의 모든 콘텐츠는 **영어**로 작성됩니다
- 다국어 운영 가이드는 `docs/i18n/`에서 관리됩니다 (JA, ZH-CN, KO, ES)
- README.md 다국어 번역은 `docs/i18n/{lang}/README.md`에 있습니다

---

Languages: [English](../../operation-guide.md) | [日本語](../ja/operation-guide.md) | [简体中文](../zh-CN/operation-guide.md) | 한국어 | [Español](../es/operation-guide.md)

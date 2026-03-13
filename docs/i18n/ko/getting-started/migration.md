# 도구 마이그레이션 가이드

## 개요

AI Dev OS의 4계층 모델은 **투자의 75% (L1-L3)**가 도구 마이그레이션에서도 유지되도록 보장합니다. **L4 (25%)** — 플러그인만 변경하면 됩니다.

## 마이그레이션 단계

### Claude Code에서 Kiro로

1. **유지**: `docs/ai-dev-os/` 서브모듈 (L1-L3 규칙) — 변경 불필요
2. **제거**: `.claude/plugins/ai-dev-os/` 서브모듈
3. **추가**: Kiro 플러그인
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-kiro.git .kiro/plugins/ai-dev-os
   cp -r .kiro/plugins/ai-dev-os/steering/ .kiro/steering/
   cp -r .kiro/plugins/ai-dev-os/hooks/ .kiro/hooks/
   ```
4. **변환**: CLAUDE.md → AGENTS.md (동일 내용, Kiro는 AGENTS.md를 읽음)
   ```bash
   cp CLAUDE.md AGENTS.md
   ```
5. **확인**: Kiro에서 `#ai-dev-os-init` 실행하여 설정 확인

### Claude Code에서 Cursor로

1. **유지**: `docs/ai-dev-os/` 서브모듈 — 변경 불필요
2. **제거**: `.claude/plugins/ai-dev-os/` 서브모듈
3. **추가**: Cursor 플러그인
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
   cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/
   ```
4. **변환**: CLAUDE.md → .cursorrules
   ```bash
   cp CLAUDE.md .cursorrules
   ```
5. **확인**: Cursor에서 `@ai-dev-os-init` 실행하여 설정 확인

### Kiro에서 Claude Code로

1. **유지**: `docs/ai-dev-os/` 서브모듈 — 변경 불필요
2. **제거**: `.kiro/steering/ai-dev-os-*` 파일 및 훅
3. **추가**: Claude Code 플러그인
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```
4. **변환**: AGENTS.md → CLAUDE.md
   ```bash
   cp AGENTS.md CLAUDE.md
   ```
5. **확인**: `/ai-dev-os-init` 실행

### Cursor에서 Claude Code로

1. **유지**: `docs/ai-dev-os/` 서브모듈 — 변경 불필요
2. **제거**: `.cursor/rules/ai-dev-os-*` 파일
3. **추가**: Claude Code 플러그인
   ```bash
   git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os
   ```
4. **변환**: .cursorrules → CLAUDE.md
   ```bash
   cp .cursorrules CLAUDE.md
   ```
5. **확인**: `/ai-dev-os-init` 실행

## 이전되는 것 (75%)

| 계층 | 내용 | 이전 여부 |
|------|------|-----------|
| L1: 철학 | `01_philosophy/` | ✅ 100% — 변경 없음 |
| L2: 판단 기준 | `02_decision-criteria/` | ✅ 100% — 변경 없음 |
| L3: 가이드라인 | `03_guidelines/` | ✅ 100% — 변경 없음 |
| L4: AI 프레임 | 플러그인별 | ❌ 새 플러그인으로 교체 |
| 컨텍스트 파일 | CLAUDE.md / AGENTS.md / .cursorrules | ⚠️ 복사 후 이름 변경 |

## 이전되지 않는 것

- 플러그인별 훅 설정
- 도구별 스킬 호출 구문 (`/` vs `#` vs `@`)
- 특정 도구 명령을 참조하는 CI/CD 통합

---

Languages: [English](../../../../getting-started/migration.md) | [日本語](../../ja/getting-started/migration.md) | [简体中文](../../zh-CN/getting-started/migration.md) | 한국어 | [Español](../../es/getting-started/migration.md)

# 빠른 시작 가이드

## 가장 빠른 방법: CLI

```bash
# 대화형 — 언어와 도구를 묻습니다
npx ai-dev-os init

# 또는 직접 지정:
npx ai-dev-os init --rules typescript --plugin claude-code
npx ai-dev-os init --rules python --plugin kiro
npx ai-dev-os init --rules typescript --plugin cursor
```

> 하나의 명령으로 서브모듈을 추가하고, 템플릿을 복사하고, 훅을 병합합니다.
> 모든 옵션은 [AI Dev OS CLI](https://github.com/yunbow/ai-dev-os-cli)를 참조하세요.

---

## 수동 설정

### 언어 규칙 선택

| 언어 | 리포지토리 | 명령어 |
|------|-----------|--------|
| TypeScript / Next.js | [ai-dev-os-rules-typescript](https://github.com/yunbow/ai-dev-os-rules-typescript) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os` |
| Python / FastAPI | [ai-dev-os-rules-python](https://github.com/yunbow/ai-dev-os-rules-python) | `git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os` |

## 도구 플러그인 선택

| 도구 | 리포지토리 | 설정 |
|------|-----------|------|
| Claude Code | [ai-dev-os-plugin-claude-code](https://github.com/yunbow/ai-dev-os-plugin-claude-code) | `git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os` |
| Kiro | [ai-dev-os-plugin-kiro](https://github.com/yunbow/ai-dev-os-plugin-kiro) | 스티어링 규칙을 `.kiro/steering/`에 복사 |
| Cursor | [ai-dev-os-plugin-cursor](https://github.com/yunbow/ai-dev-os-plugin-cursor) | 규칙을 `.cursor/rules/`에 복사 |

## 예제: TypeScript + Claude Code

```bash
cd /path/to/your-project

# 1. 규칙 추가
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. 플러그인 추가
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. CLAUDE.md 설정
cp docs/ai-dev-os/templates/nextjs/CLAUDE.md.template ./CLAUDE.md

# 4. 설정 마법사 실행 (터미널이 아닌 Claude Code 채팅에서 입력)
# /ai-dev-os-init
```

## 예제: Python + Claude Code

```bash
cd /path/to/your-project

# 1. 규칙 추가
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. 플러그인 추가
git submodule add https://github.com/yunbow/ai-dev-os-plugin-claude-code.git .claude/plugins/ai-dev-os

# 3. CLAUDE.md 설정
cp docs/ai-dev-os/templates/python-cli/CLAUDE.md.template ./CLAUDE.md

# 4. 설정 마법사 실행 (터미널이 아닌 Claude Code 채팅에서 입력)
# /ai-dev-os-init
```

## 예제: Python + Kiro

```bash
cd /path/to/your-project

# 1. 규칙 추가
git submodule add https://github.com/yunbow/ai-dev-os-rules-python.git docs/ai-dev-os
git submodule update --init

# 2. 플러그인 추가
git clone https://github.com/yunbow/ai-dev-os-plugin-kiro.git
cp -r ai-dev-os-plugin-kiro/steering/ .kiro/steering/
cp -r ai-dev-os-plugin-kiro/hooks/ .kiro/hooks/
rm -rf ai-dev-os-plugin-kiro  # 클론된 디렉토리 정리

# 3. 설정 마법사 실행 (터미널이 아닌 Kiro 채팅에서 입력)
# #ai-dev-os-init
```

## 예제: TypeScript + Cursor

```bash
cd /path/to/your-project

# 1. 규칙 추가
git submodule add https://github.com/yunbow/ai-dev-os-rules-typescript.git docs/ai-dev-os
git submodule update --init

# 2. 플러그인 추가
git submodule add https://github.com/yunbow/ai-dev-os-plugin-cursor.git .cursor/plugins/ai-dev-os
cp -r .cursor/plugins/ai-dev-os/rules/ .cursor/rules/

# 3. 설정 마법사 실행 (터미널이 아닌 Cursor 채팅에서 입력)
# @ai-dev-os-init
```

## 규칙 업데이트

```bash
git submodule update --remote docs/ai-dev-os
```

## 특정 버전 고정

```bash
cd docs/ai-dev-os
git checkout v1.2.0
cd ../..
git add docs/ai-dev-os
git commit -m "chore: pin ai-dev-os to v1.2.0"
```

## 서브모듈 문제 해결

| 문제 | 해결 방법 |
|------|-----------|
| `git clone` 후 `docs/ai-dev-os/` 디렉토리가 비어 있음 | `git submodule update --init --recursive` 실행 |
| 서브모듈이 `(not initialized)`로 표시됨 | `git submodule init && git submodule update` 실행 |
| CI 파이프라인에서 파일 누락으로 실패 | CI 설정 단계에 `git submodule update --init --recursive` 추가 |
| 항상 서브모듈과 함께 클론하고 싶음 | `git clone --recurse-submodules <url>` 사용 |
| 서브모듈이 이전 커밋을 가리킴 | `git submodule update --remote docs/ai-dev-os` 실행으로 최신 버전 가져오기 |

---

Languages: [English](../../../../getting-started/quick-start.md) | [日本語](../../ja/getting-started/quick-start.md) | [简体中文](../../zh-CN/getting-started/quick-start.md) | 한국어 | [Español](../../es/getting-started/quick-start.md)

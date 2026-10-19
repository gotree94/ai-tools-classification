# opencode 연동 가이드

이 문서는 위 카테고리의 AI 도구들을 **opencode**에서 설치·활용하는 공통 방법을 정리합니다.
opencode는 Claude Code 스킬·MCP 서버·커맨드와 호환되는 부분이 많아 기존 자산을 재사용할 수 있습니다.

- opencode 문서: https://opencode.ai
- 설정 스키마: https://opencode.ai/config.json

---

## 1. 설정 파일 위치

| 범위 | 경로 |
|---|---|
| 프로젝트 설정 | `./opencode.json`, `./opencode.jsonc`, `.opencode/opencode.json` |
| 전역 설정 | `~/.config/opencode/opencode.json` (**`~/.opencode/` 아님**) |
| 프로젝트 스킬 | `.opencode/skill(s)/<name>/SKILL.md` |
| 전역 스킬 | `~/.config/opencode/skill(s)/<name>/SKILL.md` |
| 프로젝트 에이전트 | `.opencode/agent(s)/<name>.md` |
| 프로젝트 커맨드 | `.opencode/command(s)/<name>.md` |

> **Windows 경로**: `~` = `C:\Users\Administrator`. 전역 스킬은
> `C:\Users\Administrator\.config\opencode\skills\<name>\SKILL.md` 입니다.

설정은 **시작 시 1회 로드**됩니다. 파일을 바꾼 뒤에는 opencode를 **재시작**하세요.

---

## 2. 스킬 설치 (SKILL.md)

opencode는 `**/SKILL.md`를 스킬로 인식합니다. 폴더명이 곧 스킬 이름입니다.

### 방법 A — 범용 설치기 사용
```bash
npx skills add <owner>/<repo>
```

### 방법 B — Claude Code 스킬 재사용 (자동)
opencode는 아래 경로를 **자동 스캔**합니다. Claude Code에 이미 설치했다면 그대로 사용됩니다.
- `~/.claude/skills/<name>/SKILL.md`
- `~/.agents/skills/<name>/SKILL.md`

### 방법 C — 수동 복사 (Windows)
```powershell
# 전역 스킬로 복사
xcopy /E /I "<repo>\skills\<name>" "$env:USERPROFILE\.config\opencode\skills\<name>"
```

### 방법 D — 비기본 경로 등록
```json
{
  "$schema": "https://opencode.ai/config.json",
  "skills": {
    "paths": [".opencode/skills", "C:/path/to/skills"],
    "urls": ["https://example.com/.well-known/skills/"]
  }
}
```

### SKILL.md 형식
```markdown
---
name: my-skill
description: 무엇을 하는지 + 언제 쓸지(트리거 키워드 포함). 필수.
---

# My Skill
(지침·예시·참고자료)
```
- `name`은 소문자-하이픈, 폴더명과 일치
- `description`이 없으면 모델에 노출되지 않음 → **반드시** 작성

---

## 3. MCP 서버 연동

`mcp`는 서버 이름으로 키를 잡는 객체이며 `type`이 필수입니다.

### 로컬 서버
```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "playwright": {
      "type": "local",
      "command": ["npx", "-y", "@playwright/mcp"],
      "enabled": true,
      "environment": { "BROWSER": "chromium" }
    }
  }
}
```
> `command`는 **문자열 배열**입니다(단일 문자열 불가).

### 원격 서버
```json
{
  "mcp": {
    "higgsfield": {
      "type": "remote",
      "url": "https://higgsfield.ai/mcp",
      "enabled": true,
      "headers": { "Authorization": "Bearer {env:HIGGSFIELD_API_KEY}" }
    }
  }
}
```
> 헤더/환경변수 값에서 `{env:VAR}` 보간을 지원합니다(`${VAR}` 아님). 비밀값은 파일에 하드코딩하지 마세요.

### 이 저장소에서 바로 쓸 수 있는 MCP
| 도구 | 카테고리 | 비고 |
|---|---|---|
| 21st MCP | 1 | UI 컴포넌트 |
| claude-mem | 4 | OpenCode 공식 지원 |
| ai-memory | 4 | OpenCode 지원 |
| OmniRoute | 3 | OpenAI 호환(provider로 등록) |
| OpenShell | 3 | 문서에서 opencode 실행 예시 |
| OpenRig | 3 | MCP 도구(`rig_*`) |
| Higgsfield | 5 | remote MCP |
| REA | 6 | 리버스 엔지니어링 |
| Playwright | 6 | e2e 테스트 |
| Notion / Supabase / Vercel | 7 | SaaS 연동 |

---

## 4. 커맨드 재사용 (플러그인 → opencode)

Claude Code 플러그인의 슬래시 커맨드(`command/*.md`)는 opencode 커맨드 폴더로 복사해 재사용합니다.
```powershell
xcopy /E /I "<claude-plugin-dir>\command" "$env:USERPROFILE\.config\opencode\command"
```
커맨드 파일 형식:
```markdown
---
description: 커맨드 설명
agent: build
---
여기에 프롬프트. $ARGUMENTS 로 입력을 받습니다.
```

예: Impeccable의 `/impeccable`, Diagram Design의 `/export-diagram`, Ponytail의 `/ponytail`,
CLI-Anything의 `/cli-anything` 등을 옮겨 쓸 수 있습니다.

---

## 5. provider (LLM 라우팅)

**OmniRoute** 처럼 OpenAI 호환 엔드포인트는 커스텀 provider로 등록합니다.
```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "omniroute": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "OmniRoute",
      "options": {
        "baseURL": "http://localhost:20128/v1",
        "apiKey": "{env:OMNIROUTE_API_KEY}"
      },
      "models": { "auto": { "name": "Auto" } }
    }
  },
  "model": "omniroute/auto"
}
```
`model` 값은 항상 `provider/model-id` 형식입니다.

---

## 6. 공통 규약 파일 (AGENTS.md)

opencode는 `instructions`에 지정한 파일을 항상 읽습니다. 여러 도구가 `AGENTS.md` 규약을
공유하므로(Ponytail, DSH, Matt Pocock 등) 한 파일로 지침을 통일할 수 있습니다.
```json
{
  "$schema": "https://opencode.ai/config.json",
  "instructions": ["AGENTS.md", "docs/style.md"]
}
```

---

## 7. 자주 쓰는 패턴 요약

| 하고 싶은 것 | 방법 |
|---|---|
| Claude용 스킬 쓰기 | `~/.claude/skills/`에 두면 자동 인식 |
| MCP 붙이기 | `opencode.json`의 `mcp`에 `type`과 함께 등록 |
| 슬래시 커맨드 추가 | `.opencode/command/<name>.md` 생성 |
| 여러 스킬 폴더 등록 | `skills.paths` 배열 |
| 비밀값 관리 | `{env:VAR}` 보간 사용, 파일에 하드코딩 금지 |
| 설정 반영 | **opencode 재시작** |

---

## 8. 문제 해결

- 설정이 깨져 opencode가 안 켜질 때:
  - `OPENCODE_DISABLE_PROJECT_CONFIG=1` 로 실행(전역 설정만으로 부팅) → 파일 수정 → 재시작
  - `OPENCODE_CONFIG=/path/to/file.json` 로 별도 설정 로드
- 외부 스킬 스캔을 끄고 싶을 때: `OPENCODE_DISABLE_EXTERNAL_SKILLS=1`
- Claude Code 스킬 스캔만 끄기: `OPENCODE_DISABLE_CLAUDE_CODE_SKILLS=1`

---

## 9. 카테고리별 문서 바로가기

1. [디자인 / UI·UX 스킬](./01-design-uiux/README.md)
2. [범용 스킬 / 에이전트 확장](./02-general-skills/README.md)
3. [에이전트 실행 환경 / 인프라 / 브라우저](./03-agent-runtime/README.md)
4. [메모리 도구](./04-memory/README.md)
5. [영상 / 음성 / 미디어 제작](./05-video-audio-media/README.md)
6. [개발 · 하드웨어 · 리버스 엔지니어링](./06-dev-hardware-re/README.md)
7. [서비스형 AI · 개발 툴](./07-saas-ai/README.md)
8. [프롬프트 / 학습 자료](./08-prompt-learning/README.md)
9. [Claude 무료 계정으로 가능한 것](./09-claude-free/README.md)
10. [기타](./10-misc/README.md)

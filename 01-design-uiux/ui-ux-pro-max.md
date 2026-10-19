# UI UX Pro Max

## 개요
AI 에이전트에 디자인 지식 베이스를 붙여주는 스킬입니다. 색상·타이포·레이아웃·접근성 등의
베스트 프랙티스를 에이전트가 참조하게 만듭니다.

- 저장소: https://github.com/nextlevelbuilder/ui-ux-pro-max-skill

## 설치

### CLI (권장)
```bash
npx uipro init --ai claude           # 프로젝트 로컬 설치
npx uipro init --ai claude --global  # 전역(모든 프로젝트) 설치
```

최신 버전으로 갱신:
```bash
npx uipro update
```

### Claude Code 플러그인
```bash
/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill
/plugin install ui-ux-pro-max
```

## 사용법
설치 후 별도 명령 없이 자동 활성화되며, UI/UX 관련 요청에 지식 베이스를 활용합니다.

```
"이 랜딩 페이지 색상 팔레트를 접근성 기준으로 개선해줘"
"모바일 우선 반응형 레이아웃으로 바꿔줘"
```

## opencode 연동
스킬 폴더(`SKILL.md`)를 그대로 복사하거나 `skills.paths`로 등록합니다.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "skills": { "paths": [".opencode/skills"] }
}
```

설치 스크립트가 만든 `SKILL.md` 디렉터리를 `.opencode/skills/ui-ux-pro-max/`로 복사하면
opencode가 자동으로 인식합니다.

## 주의
- Claude.ai 웹의 ZIP 업로드는 파일 수 제한(200개 초과)으로 현재 지원되지 않습니다.

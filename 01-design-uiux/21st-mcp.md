# 21st MCP

## 개요
**21st.dev**가 제공하는 UI 컴포넌트 카탈로그용 MCP 서버입니다. 에이전트가 shadcn/Tailwind 계열
UI 컴포넌트를 검색·설치할 수 있게 해줍니다.

## 사전 준비
- Node.js 18+
- 21st.dev API 키 (사이트에서 발급)

## 설치

### Claude Code
```bash
claude mcp add 21st --env API_KEY=<YOUR_KEY> -- npx -y @21st-dev/magic
```

### opencode (`opencode.json`)
```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "21st": {
      "type": "local",
      "command": ["npx", "-y", "@21st-dev/magic"],
      "enabled": true,
      "environment": { "API_KEY": "{env:TWENTYFIRST_API_KEY}" }
    }
  }
}
```
`OPENCODE`는 헤더/환경변수에서 `{env:VAR}` 보간을 지원하므로 키를 파일에 하드코딩하지 마세요.

## 사용법
에이전트에게 자연어로 요청하면 됩니다.
```
"가격 카드 섹션 UI 컴포넌트를 만들어줘 (21st 사용)"
"pricing table 컴포넌트 검색해서 프로젝트에 추가해줘"
```

## 활용 팁
- 프로젝트에 shadcn/ui가 이미 있으면 스타일이 자동으로 맞춰집니다.
- 컴포넌트를 먼저 검색 → 선택 → 설치 순으로 진행하면 불필요한 코드가 줄어듭니다.

## 링크
- https://21st.dev

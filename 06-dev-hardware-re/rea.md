# REA — Reverse Engineer Anything

## 개요
바이너리·앱·런타임 동작을 리버스 엔지니어링하는 **MCP 서버 + CLI**입니다.
네이티브 바이너리(Ghidra/IDA/Hopper), JS/Electron 앱, .NET 어셈블리, Android APK, 펌웨어,
웹사이트 등을 로컬에서 분석합니다. 모든 결론에 근거(evidence)를 제공합니다. MIT, 139개 도구.

- 저장소: https://github.com/morluto/rea

## 요구 사항
- **Node.js 22.x(≥22.19) / 24.x / 26+**
- npm
- 네이티브 분석 시 Hopper / Ghidra / IDA 선택적

## 설치
```bash
npx rea-agents setup                       # 에이전트에 MCP 등록 (Claude Code/Codex/Cursor/Gemini/Grok 등)
npm install --global rea-agents            # rea CLI 상시 설치
rea --help
```

> README에 유사 repo명 주의 경고가 있습니다. 공식은 `morluto/rea`입니다.

## 사용법
```bash
npx -y rea-agents@latest analyze-javascript-application /path/to/app --json
```
에이전트에게 자연어로 질의:
```
"Notes 앱의 검색이 어떻게 동작하는지 근거와 함께 알려줘"
```

macOS / Windows / Linux 지원.

## opencode 연동
`npx rea-agents setup`이 MCP 설정을 추가하거나, 수동으로 등록합니다.
```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "rea": {
      "type": "local",
      "command": ["npx", "-y", "rea-agents", "mcp"],
      "enabled": true
    }
  }
}
```
> 실제 MCP 서브커맨드는 버전에 따라 다를 수 있으니 `rea --help`로 확인하세요.

## 링크
- https://github.com/morluto/rea
- https://rea.tools

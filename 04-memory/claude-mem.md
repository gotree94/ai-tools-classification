# claude-mem

## 개요
세션 간 **지속 컨텍스트**를 제공하는 메모리 압축 시스템입니다. 에이전트의 도구 사용을 자동
캡처 → AI로 압축·요약 → 다음 세션에 관련 컨텍스트를 주입합니다.
SQLite + Chroma 벡터 DB로 하이브리드 검색을 수행하며, Claude Code·**OpenCode**·Codex·Cursor·
Gemini·Copilot 등을 지원합니다.

- 저장소: https://github.com/thedotmack/claude-mem

## 설치

### 권장
```bash
npx claude-mem install
```

### Claude Code 플러그인
```
/plugin marketplace add thedotmack/claude-mem
/plugin install claude-mem
```

요구 사항: Node.js 20+, Bun(auto), uv(auto)
> `npm install -g claude-mem`은 SDK만 설치하므로 권장하지 않습니다.

## 사용법
설치 후 자동 작동합니다(SessionStart 훅으로 이전 세션 컨텍스트 자동 주입).
검색은 MCP 도구로 진행합니다.
```
search(query="authentication bug", type="bugfix", limit=10)  # 레이어1: 인덱스
timeline(anchor=12345, depth_before=5, depth_after=5)        # 레이어2: 타임라인
get_observations(ids=[123, 456])                             # 레이어3: 전체 상세
```
3레이어 progressive disclosure로 약 10배 토큰 절감. Web 뷰어: `http://localhost:37777`.

## 연동
- 라이프사이클 훅(SessionStart/PreToolUse/PostToolUse/Stop/SessionEnd)
- **MCP 서버**(search / timeline / get_observations)
- 로컬 워커 서비스(HTTP API) + `mem-search` 스킬

## opencode 연동
claude-mem은 **OpenCode를 공식 지원**합니다. 설치 스크립트가 opencode 설정에 MCP 서버를
자동 등록합니다. 수동 등록 시:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "claude-mem": {
      "type": "local",
      "command": ["npx", "-y", "claude-mem-mcp"],
      "enabled": true
    }
  }
}
```
> 정확한 MCP 실행 명령은 설치 버전에 따라 다를 수 있으니 `npx claude-mem install`이 생성한
> 설정을 우선 사용하세요.

## 링크
- https://github.com/thedotmack/claude-mem

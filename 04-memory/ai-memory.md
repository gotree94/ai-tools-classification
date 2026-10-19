# ai-memory

## 개요
"ai-memory" 이름의 **저장소가 2개** 존재합니다. 문서화 시 어느 쪽인지 명시가 필요합니다.

- **(A) akitaonrails/ai-memory** — Rust, 20+ 하네스 공유, **git 기반 마크다운 위키**,
  서버-클라이언트 구조, 팀 공유 지원, LLM 0회로 동작
- **(B) alphaonedev/ai-memory-mcp** — MCP 전용, SQLite, `memory_store`/`recall` 등 다수 도구

## (A) akitaonrails/ai-memory

### 설치
```bash
curl -fsSL https://github.com/akitaonrails/ai-memory/releases/latest/download/install.sh | sh
ai-memory setup    # MCP·훅·스킬 자동 와이링 (agent별 확인 후 y)
```
지원: Claude Code, Codex, **OpenCode**, Cursor, Gemini CLI, Grok, Devin, Kimi, Kiro, Copilot CLI 등 30종+
플랫폼: Linux / macOS / WSL2

### 사용법
```bash
ai-memory run codex
```
Claude 세션의 히스토리를 투영하고 핸드오프 프로토콜로 다음 에이전트가 이어서 작업합니다.
세션 종료 시 관측이 마크다운 위키 페이지로 통합되고, 다음 세션 시작 시 bounded brief가 주입됩니다.
검색은 full-text·엔티티·링크(+선택적 벡터). 팀은 하나의 서버를 공유합니다.

## (B) alphaonedev/ai-memory-mcp

### 설치 (MCP 서버)
```json
{
  "mcpServers": { "memory": {
      "command": "ai-memory",
      "args": ["--db", "~/.claude/ai-memory.db", "mcp", "--tier", "semantic"] } }
}
```
크레이트/npm/PyPI 배포. 티어: `keyword` / `semantic` / `smart` / `autonomous`

### 사용법
MCP 설정 후 에이전트가 자동으로 `memory_store` / `memory_recall` / `memory_search`를 호출합니다.
```
"우리가 PostgreSQL 15를 쓴다는 걸 기억해줘"
```

## opencode 연동
(A)는 OpenCode를 support-matrix에 포함하며 `ai-memory setup`이 MCP 등록을 자동화합니다.
수동 등록 시:
```json
{
  "mcp": {
    "memory": {
      "type": "local",
      "command": ["ai-memory", "--db", "~/.claude/ai-memory.db", "mcp", "--tier", "semantic"],
      "enabled": true
    }
  }
}
```

## 링크
- https://github.com/akitaonrails/ai-memory
- https://github.com/alphaonedev/ai-memory-mcp

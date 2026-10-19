# OpenRig

## 개요
Claude Code·Codex·Pi 등 여러 코딩 에이전트를 YAML(**RigSpec**)로 정의해 **tmux 세션 기반의
영구 "에이전트 팀"** 으로 운영하는 멀티 에이전트 오케스트레이션 도구입니다.
리드 에이전트와 대화하면 팀 전체를 조율합니다. (약 7,900 ★)

- 저장소: https://github.com/mvschwarz/openrig

## 요구 사항
- Node.js 22/24
- tmux
- macOS / Linux (Windows는 **WSL2**)

## 설치
```bash
npm install -g @openrig/cli
rig setup --dry-run
rig setup --providers claude   # 또는 codex
```

### 원라인 설치
```bash
curl -fsSL https://raw.githubusercontent.com/mvschwarz/openrig/v0.6.11/scripts/install.sh | sh
```

## 사용법
```bash
rig up starter --cwd .              # starter 팀(빌더+리뷰어) 부팅
rig send dev-build@starter 'Implement <change>. Track the task...'
rig queue list --destination dev-build@starter
rig terminal open saved:kernel --window
rig tui                             # 팀 대시보드
```

### 내장 팀
`starter`(2인), `workshop`(4인), `factory`(7인), `code-review`, `research`, `pm`

## 연동
- 로컬 데몬 + CLI(`rig`) + TUI
- **MCP 서버** 제공(`rig_up`, `rig_ps`, `rig_send` 등) → 에이전트가 자기 토폴로지를 관리
- Claude Code / Codex 네이티브 세션 구동, `openrig-skills` 시드

## opencode 연동
opencode를 팀원 에이전트로 지정할 수 있습니다(RigSpec에 실행 명령 지정). 또는 제공되는
**MCP 서버**를 opencode에 등록해 `rig_*` 도구를 쓰게 합니다.

```json
{
  "mcp": {
    "openrig": { "type": "local", "command": ["rig", "mcp"], "enabled": true }
  }
}
```
> 실제 MCP 실행 인자는 버전에 따라 다를 수 있으니 저장소 README를 확인하세요.

## 링크
- https://github.com/mvschwarz/openrig

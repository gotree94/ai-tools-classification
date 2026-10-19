# 2. 범용 스킬 / 에이전트 확장

여러 에이전트(Claude Code·Codex·Cursor·Gemini CLI·opencode 등)에 공통으로 쓸 수 있는
스킬 모음과 확장 도구입니다.

## 도구 목록

| 도구 | 한 줄 요약 | 문서 |
|---|---|---|
| mattpocock/skills | TypeScript/엔지니어링 중심 스킬 모음(26종) | [mattpocock-skills.md](./mattpocock-skills.md) |
| agent-skills | Vercel Labs 스킬 모음 | [agent-skills.md](./agent-skills.md) |
| skills | Anthropic 공식 스킬 모음 | [anthropic-skills.md](./anthropic-skills.md) |
| cursor/plugins | Cursor 공식 플러그인 | [cursor-plugins.md](./cursor-plugins.md) |
| CLI-Anything | GUI 앱을 CLI로 제어하게 해주는 도구 | [cli-anything.md](./cli-anything.md) |
| Agent-Reach | 에이전트에 인터넷 접근 능력 부여 | [agent-reach.md](./agent-reach.md) |

## 공통 설치 패턴
```bash
npx skills add <owner>/<repo>
```

## opencode 연동 요약
- 대부분 `SKILL.md` 스킬 → `.opencode/skills/<name>/` 또는 `~/.config/opencode/skills/`로 복사.
- opencode는 `~/.claude/skills/`, `~/.agents/skills/`도 자동 스캔하므로 기존 설치를 재사용할 수 있습니다.
- 자세한 내용은 [../OPENCODE.md](../OPENCODE.md) 참고.

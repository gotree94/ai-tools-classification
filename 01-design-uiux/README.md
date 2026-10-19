# 1. 디자인 / UI·UX 스킬 (Claude Code용)

대부분 **에이전트 스킬(SKILL.md)** 형식이거나 **플러그인 마켓플레이스**로 설치합니다.
opencode 연동은 [../OPENCODE.md](../OPENCODE.md)의 공통 패턴을 참고하세요.

## 도구 목록

| 도구 | 한 줄 요약 | 문서 |
|---|---|---|
| 21st MCP | UI 컴포넌트용 MCP | [21st-mcp.md](./21st-mcp.md) |
| UI UX Pro Max | AI용 디자인 지식 베이스 + 스킬 | [ui-ux-pro-max.md](./ui-ux-pro-max.md) |
| Vercel Web Design Guidelines | Vercel 공식 웹 디자인 가이드라인 스킬 | [vercel-web-design.md](./vercel-web-design.md) |
| Emil Kowalski Skills | 애니메이션·인터랙션 스킬 모음 | [emil-kowalski-skills.md](./emil-kowalski-skills.md) |
| Taste Skill | 미적 판단(취향) 스킬 | [taste-skill.md](./taste-skill.md) |
| Hallmark | 프론트엔드 품질 스킬 | [hallmark.md](./hallmark.md) |
| Impeccable | UI 완성도 높이는 24개 커맨드 스킬 | [impeccable.md](./impeccable.md) |
| Anthropic frontend-design | Anthropic 공식 프론트엔드 디자인 스킬 | [anthropic-frontend-design.md](./anthropic-frontend-design.md) |
| Diagram Design | 다이어그램 생성 스킬 | [diagram-design.md](./diagram-design.md) |
| Archify | 아키텍처 다이어그램 스킬 *(확인 필요)* | [archify.md](./archify.md) |

## 공통 설치 패턴 (스킬)

```bash
# 대부분의 스킬은 skills.sh 또는 npx skills 로 설치
npx skills add <owner>/<repo>

# Claude Code 플러그인 마켓플레이스로 설치하는 경우
/plugin marketplace add <owner>/<repo>
/plugin install <skill>@<marketplace>
```

## 공통 설치 패턴 (MCP)

Claude Code:
```bash
claude mcp add <name> -- npx -y <package>
```

opencode (`opencode.json`):
```json
{
  "mcp": {
    "<name>": { "type": "local", "command": ["npx", "-y", "<package>"], "enabled": true }
  }
}
```

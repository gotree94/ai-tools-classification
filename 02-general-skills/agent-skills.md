# agent-skills (Vercel Labs)

## 개요
**Vercel Labs**의 에이전트 스킬 모음 저장소입니다. 웹 디자인 가이드라인을 포함해 여러
실무 스킬을 제공합니다.

- 저장소: https://github.com/vercel-labs/agent-skills

## 설치

### 스킬 단독 설치
```bash
npx skills add vercel-labs/agent-skills
```

### Claude Code 플러그인
```bash
/plugin marketplace add vercel-labs/agent-skills
/plugin install <skill-name>@agent-skills
```

## 사용법
스킬별 트리거는 각 `SKILL.md`의 description을 따릅니다.

## opencode 연동
```bash
git clone --depth 1 https://github.com/vercel-labs/agent-skills
xcopy /E /I agent-skills\skills\web-design-guidelines %USERPROFILE%\.config\opencode\skills\web-design-guidelines
```

## 주의
목록의 "agent-skills"와 "skills"는 이름이 모호합니다. 이 저장소(vercel-labs)와
[anthropic-skills.md](./anthropic-skills.md)(anthropics/skills)가 가장 유력합니다.

## 링크
- https://github.com/vercel-labs/agent-skills

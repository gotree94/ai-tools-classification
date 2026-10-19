# Vercel Web Design Guidelines

## 개요
Vercel Labs의 **agent-skills** 저장소에 포함된 웹 디자인 가이드라인 스킬입니다.
접근성·레이아웃·반응형·성능 관점의 프론트엔드 규칙을 에이전트가 따르도록 합니다.

- 저장소: https://github.com/vercel-labs/agent-skills/tree/main/skills/web-design-guidelines

## 설치

### 스킬 단독 설치 (범용)
```bash
npx skills add vercel-labs/agent-skills
```

### Claude Code 플러그인
```bash
/plugin marketplace add vercel-labs/agent-skills
/plugin install web-design-guidelines@agent-skills
```

## 사용법
설치 후 UI 코드를 작성/리뷰할 때 규칙이 자동 적용됩니다.

```
"이 컴포넌트를 Vercel 웹 디자인 가이드라인에 맞춰 리뷰해줘"
"접근성 위반 항목을 찾아 고쳐줘"
```

## opencode 연동
`vercel-labs/agent-skills`의 `skills/web-design-guidelines/SKILL.md`를
`.opencode/skills/web-design-guidelines/`로 복사하면 자동 로드됩니다.

```bash
git clone --depth 1 https://github.com/vercel-labs/agent-skills
cp -r agent-skills/skills/web-design-guidelines ~/.config/opencode/skills/
```
(Windows: `xcopy` 또는 탐색기 복사)

## 링크
- https://github.com/vercel-labs/agent-skills

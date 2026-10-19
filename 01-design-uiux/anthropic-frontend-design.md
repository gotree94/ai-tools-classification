# Anthropic frontend-design

## 개요
**Anthropic 공식** 스킬 저장소(`anthropics/skills`)에 포함된 프론트엔드 디자인 스킬입니다.
깔끔하고 실용적인 웹 UI를 생성하는 지침을 제공합니다.

- 저장소: https://github.com/anthropics/skills/tree/main/skills/frontend-design

## 설치

### Claude Code 플러그인
```bash
/plugin marketplace add anthropics/skills
/plugin install example-skills@anthropic-agent-skills
# 문서 생성 스킬까지 필요하면:
/plugin install document-skills@anthropic-agent-skills
```

### 스킬 단독 설치
```bash
npx skills add anthropics/skills
```

## 사용법
```
"이 디자인 시안을 HTML/CSS 프론트엔드로 구현해줘"
"모던한 랜딩 페이지 마크업을 만들어줘"
```

## opencode 연동
opencode는 `~/.claude/skills/`를 **자동 스캔**합니다. Claude Code에 설치했다면 대개
그대로 사용 가능하며, 아니라면 복사합니다.

```bash
git clone --depth 1 https://github.com/anthropics/skills
xcopy /E /I skills\skills\frontend-design %USERPROFILE%\.config\opencode\skills\frontend-design
```

## 스킬 템플릿 frontmatter
직접 스킬을 만들 때 필수 필드는 `name`, `description` 두 개뿐입니다.

## 링크
- https://github.com/anthropics/skills

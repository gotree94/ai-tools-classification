# skills (Anthropic 공식)

## 개요
**Anthropic 공식 스킬 저장소**입니다. 문서 생성(document-skills), 프론트엔드 디자인,
예제 스킬(example-skills) 등을 제공합니다. 목록의 "skills" 항목으로 가장 유력합니다.

- 저장소: https://github.com/anthropics/skills

## 설치

### Claude Code 플러그인
```bash
/plugin marketplace add anthropics/skills
/plugin install example-skills@anthropic-agent-skills
/plugin install document-skills@anthropic-agent-skills
```

### 스킬 단독 설치
```bash
npx skills add anthropics/skills
```

## 사용법
문서 스킬 설치 시 docx/pdf/pptx/xlsx 생성·편집 능력이 추가됩니다.
```
"이 내용을 PDF로 만들어줘"
"이 표를 엑셀 파일로 변환해줘"
```

## opencode 연동
opencode는 `~/.claude/skills/`를 자동 스캔합니다. 별도 설치가 어렵다면 저장소를 clone 하여
원하는 스킬 폴더만 복사:
```bash
xcopy /E /I skills\skills\frontend-design %USERPROFILE%\.config\opencode\skills\frontend-design
```

## 스킬 작성 규칙
필수 frontmatter는 `name`, `description` 두 개입니다.

## 링크
- https://github.com/anthropics/skills
- https://docs.claude.com/en/docs/agents-and-tools/agent-skills

# mattpocock/skills

## 개요
TypeScript/엔지니어링 실무 중심의 스킬 모음(**26종**). `user-invoked` / `model-invoked`
두 축으로 나뉘어, 사용자가 직접 부르는 스킬과 모델이 자동 호출하는 스킬을 구분합니다.

- 저장소: https://github.com/mattpocock/skills

## 설치

### Claude Code
```bash
/plugin marketplace add mattpocock/skills
/plugin install <skill-name>
```

### Gemini CLI
```bash
gemini skills install mattpocock/skills --path skills/engineering
gemini skills install mattpocock/skills --path skills/productivity
```
> Gemini CLI는 스킬을 **수동으로 갱신**해야 합니다.

### GitHub Copilot
`~/.copilot/settings.json`에 `extraKnownMarketplaces` 항목을 추가합니다(저장소 INSTALL 안내 참고).

### 범용
```bash
npx skills add mattpocock/skills
```

## 사용법
```
"이 TypeScript 코드를 타입 안전하게 리팩터링해줘"
"테스트를 추가하고 엣지 케이스를 정리해줘"
```

## opencode 연동
`skills/engineering`, `skills/productivity` 하위의 `SKILL.md`를 각각 복사합니다.
```bash
xcopy /E /I skills\engineering %USERPROFILE%\.config\opencode\skills\engineering
```

## 링크
- https://github.com/mattpocock/skills

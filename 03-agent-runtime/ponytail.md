# Ponytail *(확인 필요 → 정상 확인됨)*

## 개요
AI 에이전트에 **"게으른 시니어 개발자" 사고방식**(YAGNI·최소 코드)을 주입하는 프롬프트
스킬입니다. 벤치마크 기준 코드 -53%, 토큰 -45%, 비용 -26%이며 위험 로직 98%가 테스트를
동반합니다. Claude Code·Codex·**OpenCode** 등 20종 에이전트를 지원합니다. (매우 활발)

- 저장소: https://github.com/DietrichGebert/ponytail

## 설치

### Claude Code
```
/plugin marketplace add DietrichGebert/ponytail
/plugin install ponytail@ponytail
```

### Codex
```bash
codex plugin marketplace add DietrichGebert/ponytail
codex plugin add ponytail@ponytail
```

### 그 외 에이전트
- `AGENTS.md`를 프로젝트에 복사, 또는
- `skills/ponytail/SKILL.md`를 스킬로 설치 (INSTALL.md 참고)

## 사용법
세션 전반에서 자동 활성화됩니다.
```
/ponytail [lite|full|ultra|off]   # 강도 설정
/ponytail-review                  # 현재 diff를 시니어 수준으로 리뷰
/ponytail-audit                   # 전체 레포 우선순위 감사
/ponytail-debt                    # shortcut: 주석을 부채 대장부로 수집
/ponytail band                    # Claude Code용 비용·토큰 밴드 표시
```

## opencode 연동
스킬(`SKILL.md`)을 복사하거나 `AGENTS.md` 규칙을 프로젝트 루트에 두면 됩니다.

```bash
xcopy /E /I ponytail\skills\ponytail %USERPROFILE%\.config\opencode\skills\ponytail
```
또는 프로젝트에:
```json
{ "$schema": "https://opencode.ai/config.json", "instructions": ["AGENTS.md"] }
```

## 지원 어댑터
스킬 파일, `AGENTS.md`, Cursor rules, Windsurf/Cline/Copilot/Kiro, npm 패키지(`@dietrichgebert/ponytail`).

## 링크
- https://github.com/DietrichGebert/ponytail

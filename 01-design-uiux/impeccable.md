# Impeccable

## 개요
UI 완성도를 끌어올리는 **24개 슬래시 커맨드** 모음 스킬입니다.
디자인 크래프트부터 폴리싱, 감사(audit), 최적화까지 단계별로 제공합니다.

- 저장소: https://github.com/pbakaus/impeccable

## 포함 커맨드 (24종)
`craft`, `init`, `document`, `extract`, `shape`, `critique`, `audit`, `polish`,
`bolder`, `quieter`, `distill`, `harden`, `onboard`, `animate`, `colorize`,
`typeset`, `layout`, `delight`, `overdrive`, `clarify`, `adapt`, `optimize`,
`live`, `generate`

## 설치

### Claude Code 플러그인 (권장)
```bash
/plugin marketplace add pbakaus/impeccable
/plugin install impeccable
```

### 기타 설치 경로
- Git submodule
- website ZIP 다운로드 (저장소 안내 참고)

## 사용법
```
/impeccable polish src/components/Card.tsx
/impeccable audit
/impeccable bolder        # 더 과감하게
/impeccable quieter       # 더 절제되게
```

## 텔레메트리 끄기
```bash
npx impeccable telemetry off
```

## opencode 연동
플러그인의 커맨드 정의(`command/*.md`)를 opencode 명령 폴더로 복사해 재사용할 수 있습니다.

```bash
# Claude 플러그인이 설치된 위치에서 커맨드 복사
xcopy /E /I <claude-plugin-dir>\command %USERPROFILE%\.config\opencode\command
```
opencode 커맨드는 `.opencode/command/*.md`(또는 전역 `~/.config/opencode/command/`)에서 로드됩니다.

## 링크
- https://github.com/pbakaus/impeccable

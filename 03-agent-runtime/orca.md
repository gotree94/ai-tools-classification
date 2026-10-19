# Orca *(확인 필요 → 정상 확인됨)*

## 개요
여러 코딩 에이전트(Claude Code, Codex, **OpenCode**, Pi, Grok 등 40종+)를 각각 **격리된
git worktree**에서 병렬 실행·관리하는 데스크톱 오케스트레이터입니다.
"100x 빌더를 위한 AI 오케스트레이터"를 표방하며, 모바일 컴패니언 앱(iOS/Android)으로
원격 모니터링이 가능합니다.

- 저장소: https://github.com/stablyai/orca
- 다운로드: https://onorca.dev/download

## 설치

### macOS
```bash
brew install --cask stablyai/orca/orca
```

### 기타
macOS arm64/x64, Windows(.exe), Linux(AppImage) 직접 다운로드.

## 사용법
- 데스크톱 앱에서 프롬프트를 최대 **5개 에이전트의 별도 worktree**에 분배
- 결과 비교 후 승자 머지
- CLI로도 스크립팅 가능:
  ```bash
  orca worktree create / snapshot / click / fill
  ```
- **Design Mode**: Chromium 창에서 UI 요소를 클릭하면 HTML·CSS·스크린샷이 에이전트 프롬프트로 전달

## 연동
- 데스크톱 앱(내장 터미널·브라우저) + **CLI**(에이전트가 Orca를 제어) + 모바일 앱
- GitHub / Linear 네이티브 연동

## opencode 연동
Orca가 지원하는 40종+ 에이전트에 **OpenCode가 포함**되어 있습니다. Orca 설정에서 실행할
에이전트로 opencode를 선택하면 각 worktree에서 병렬 실행됩니다.

## 링크
- https://github.com/stablyai/orca

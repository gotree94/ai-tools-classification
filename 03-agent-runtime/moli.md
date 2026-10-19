# moli

## 개요
AI 에이전트용 **헤드리스 브라우저**입니다. Rust로 만든 독립 브라우저 커널(Chromium 래퍼가
아님)로, DOM 우선·온디맨드 렌더링으로 가볍고(중앙값 RSS ~73MiB) 빠릅니다.
CDP, WebDriver Classic/BiDi를 지원합니다. (약 19,700 ★)

- 저장소: https://github.com/lexmount/moli

## 설치

### Linux / macOS
```bash
curl --proto '=https' --tlsv1.2 -fsSL \
  https://github.com/lexmount/moli/releases/latest/download/moli-installer.sh | sh
```

### Windows (PowerShell)
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://github.com/lexmount/moli/releases/latest/download/moli-installer.ps1 | iex"
```

## 사용법
```bash
# 페이지를 Markdown으로 추출
moli fetch --dump markdown --wait-until done https://example.com

# 모델 친화적 시맨틱 트리 추출
moli fetch --dump semantic_tree_text --wait-selector body https://example.com

# 스크린샷 / PDF
moli fetch --layout --dump screenshot https://example.com > page.png

# 자동화 서버 시작 (CDP :9222)
moli serve --layout
```

## 에이전트 연동
- **스킬 제공**: 저장소 `/skills` 디렉터리에서 `moli-webfetch` 스킬을 설치할 수 있습니다.
- **Playwright 연결**: `chromium.connectOverCDP("http://127.0.0.1:9222")`로 기존 자동화 코드에서 재사용.
- **WebMCP 플레이그라운드** 포함.

## opencode 연동
`moli-webfetch` 스킬 폴더를 복사하거나, 셸 도구를 통해 직접 호출합니다.
```bash
xcopy /E /I moli\skills\moli-webfetch %USERPROFILE%\.config\opencode\skills\moli-webfetch
```

## 링크
- https://github.com/lexmount/moli

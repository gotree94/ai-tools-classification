# e2e (엔드투엔드 테스트)

## 개요
e2e 테스트는 **사용자 흐름 전체를 실제 환경처럼 검증**하는 테스트입니다. 특정 단일 "e2e"
도구라기보다 **개념**이며, 일반적으로 **Playwright / Cypress**가 대표 도구입니다.
참고로 `tester-army/e2e`(약 11,100 ★, 자연어 목표 → 에이전트가 앱 구동)라는 도구도 있습니다.

> 목록의 "e2e"는 모호한 항목이므로 개념 + Playwright 중심으로 정리합니다.

## 대표 도구 설치

### Playwright (2026 신규 프로젝트 표준)
```bash
npm init playwright@latest              # 테스트 러너
npm i -g @playwright/cli@latest         # 코딩 에이전트용 CLI
npx @playwright/mcp@latest              # AI 에이전트용 MCP
npx playwright test                     # 실행
```

예시 테스트:
```javascript
test('has title', async ({ page }) => {
  await page.goto('https://playwright.dev/');
  await expect(page).toHaveTitle(/Playwright/);
});
```

### 기타
- **Cypress**: `npm install cypress --save-dev` (JS 전용, 인브라우저 디버깅 강점)
- **Selenium**: 다언어, 엔터프라이즈
- **Appium**: 모바일

## opencode 연동 (권장)
Playwright **MCP**를 opencode에 등록하면 에이전트가 브라우저를 직접 조작·검증합니다.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "playwright": {
      "type": "local",
      "command": ["npx", "-y", "@playwright/mcp"],
      "enabled": true
    }
  }
}
```
그 후:
```
"로그인 → 결제 흐름의 e2e 테스트를 Playwright로 작성하고 실행해줘"
```

## 링크
- https://playwright.dev
- https://github.com/microsoft/playwright-mcp
- https://github.com/tester-army/e2e

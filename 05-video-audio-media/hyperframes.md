# HyperFrames

## 개요
HTML/CSS/미디어와 seekable 애니메이션을 **결정론적(deterministic) MP4**로 렌더링하는
오픈소스 프레임워크입니다. "Write HTML. Render video. Built for agents." HeyGen 제작, Apache-2.0.

- 저장소: https://github.com/heygen-com/hyperframes

## 요구 사항
- **Node.js 22+**
- **FFmpeg**

## 설치

### CLI 스캐폴딩
```bash
npx hyperframes init my-video
```

### AI 에이전트 플러그인 (Claude Code)
```bash
claude plugin marketplace add heygen-com/hyperframes
claude plugin install hyperframes@hyperframes
```

### 스탠드얼론 스킬 (opencode 등)
```bash
npx skills add heygen-com/hyperframes
npx hyperframes skills update
```

## 사용법
```bash
npx hyperframes init my-video
cd my-video
npx hyperframes preview      # 브라우저 라이브 리로드 미리보기
npx hyperframes render       # MP4로 렌더
npx hyperframes add data-chart   # 카탈로그 블록 설치
```

컴포지션은 `index.html` + `data-start` / `data-duration` / `data-track-index` 속성으로 구성합니다.
GSAP / CSS / Lottie / Three.js / WAAPI 어댑터를 지원하며, AWS Lambda 분산 렌더링(`cloud render`)도 가능합니다.

## opencode 연동
스탠드얼론 스킬 설치 후 `SKILL.md`를 전역 스킬로 복사하거나, 셸 도구로 `npx hyperframes`를 직접 호출합니다.
```bash
xcopy /E /I hyperframes\skills\hyperframes %USERPROFILE%\.config\opencode\skills\hyperframes
```

## 링크
- https://github.com/heygen-com/hyperframes

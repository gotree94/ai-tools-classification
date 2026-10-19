# DeepSeek Harness (dsh)

## 개요
DeepSeek AI의 오픈소스 **에이전트 하네스**입니다. "Everything is a Plugin" 아키텍처
(Cordis 프레임워크 기반)의 런타임이며 Web UI를 제공합니다. 현재 **개발자 프리뷰** 단계로
호환성이 깨지는 변경이 있을 수 있습니다.

- 저장소: https://github.com/deepseek-ai/deepseek-harness

## 설치

### npm으로 바로 실행
```bash
npx @deepseek-ai/dsh web
```

### 소스에서 빌드
```bash
git clone https://github.com/deepseek-ai/deepseek-harness.git
cd deepseek-harness
pnpm install && pnpm run build
pnpm dsh web
```

## 사용법
`npx @deepseek-ai/dsh web` 실행 → Web UI가 `http://127.0.0.1:3080`에서 열립니다.

```bash
npx @deepseek-ai/dsh web --no-open   # 브라우저 자동 열기 비활성화
```
SSH 환경에서는 URL만 출력됩니다.

## 생태계
- 플러그인 태그: `dsh-plugin`
- `.claude/`, `AGENTS.md` 규약 지원 → 기존 에이전트 설정과 호환
- 전용 데스크톱 클라이언트: [dsh-desktop.md](./dsh-desktop.md)

## opencode 연동
DSH를 MCP 클라이언트/서버로 연결하거나, 공통 `AGENTS.md` 규약을 공유해 지침을 통일할 수 있습니다.
opencode는 `AGENTS.md`를 `instructions`로 읽습니다.

```json
{
  "instructions": ["AGENTS.md"]
}
```

## 링크
- https://github.com/deepseek-ai/deepseek-harness

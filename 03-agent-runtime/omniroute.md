# OmniRoute

## 개요
MIT 라이선스 무료 **AI 게이트웨이**입니다. 375개 프로바이더(150+ 무료 티어), 1,400+ 모델을
단일 엔드포인트로 라우팅합니다. Claude Code·Codex·Cursor·**OpenCode**·Cline·Copilot 등과
호환되며, 쿼터 인식 자동 폴백과 RTK+Caveman 압축(토큰 15~95% 절감)을 제공합니다. (약 78,500 ★)

- 저장소: https://github.com/diegosouzapw/OmniRoute

## 설치

### npm
```bash
npm install -g omniroute
omniroute
```

### Docker
```bash
docker run -d --name omniroute --restart unless-stopped \
  -p 127.0.0.1:20128:20128 -v omniroute-data:/app/data diegosouzapw/omniroute:latest
```

## 사용법
1. 대시보드 `http://localhost:20128` 접속
2. **Providers**에서 프로바이더 연결
3. 코딩 도구에 아래를 설정
```
Base URL: http://localhost:20128/v1
API Key:  (Dashboard → Endpoints에서 복사)
Model:    auto
```

검증:
```bash
curl http://localhost:20128/v1/models -H "Authorization: Bearer YOUR_KEY"
```

## opencode 연동 (핵심)
OmniRoute는 **OpenAI 호환 API**이므로 opencode에서 커스텀 provider로 등록합니다.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "provider": {
    "omniroute": {
      "npm": "@ai-sdk/openai-compatible",
      "name": "OmniRoute",
      "options": {
        "baseURL": "http://localhost:20128/v1",
        "apiKey": "{env:OMNIROUTE_API_KEY}"
      },
      "models": {
        "auto": { "name": "Auto (쿼터 인식 폴백)" }
      }
    }
  },
  "model": "omniroute/auto"
}
```

## 부가 기능
- MCP / A2A 지원
- CLI: `omniroute serve --headless`
- Desktop / PWA / Electron 앱

## 링크
- https://github.com/diegosouzapw/OmniRoute

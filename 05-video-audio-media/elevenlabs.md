# ElevenLabs

## 개요
AI **음성 합성(TTS)·보이스 클로닝·더빙·음향 효과**를 제공하는 상용 AI 오디오 플랫폼입니다.
웹앱 + REST/WebSocket API를 제공합니다.

- 사이트: https://elevenlabs.io
- 문서: https://elevenlabs.io/docs

## 설치 (SDK)

### Python
```bash
pip install elevenlabs
```

### Node.js
```bash
npm install @elevenlabs/elevenlabs-js
```

## 사용법 (Python)
```python
from elevenlabs.client import ElevenLabs

client = ElevenLabs(api_key="your_api_key")
audio = client.text_to_speech.convert(
    text="Hello, world!",
    voice_id="<voice_id>",
)
```

## API / 요금
- API Key 발급 후 **문자(character) 기반 과금**
- 무료 티어 제공, 유료 구독(Starter/Creator/Pro 등)으로 캐릭터 한도 확대
- 응답 헤더 `character-cost`로 비용 확인 가능

## opencode 연동
API 기반이므로:
- 셸 도구로 SDK 스크립트를 호출하거나,
- 사내/커뮤니티 ElevenLabs **MCP 서버**를 opencode에 등록합니다.
```json
{
  "mcp": {
    "elevenlabs": {
      "type": "local",
      "command": ["npx", "-y", "elevenlabs-mcp"],
      "enabled": true,
      "environment": { "ELEVENLABS_API_KEY": "{env:ELEVENLABS_API_KEY}" }
    }
  }
}
```

## 링크
- https://elevenlabs.io
- https://github.com/elevenlabs/elevenlabs-python

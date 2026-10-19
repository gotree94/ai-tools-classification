# cursor/plugins

## 개요
**Cursor 공식 플러그인** 저장소입니다. Cursor 에디터용 플러그인/확장을 모아둔 곳으로,
에이전트 확장 및 도구 연동에 사용됩니다.

- 저장소: https://github.com/cursor/plugins

## 설치

### Cursor 에디터
Cursor의 플러그인/확장 마켓에서 설치하거나, 저장소의 설치 안내를 따릅니다.

### CLI 예시 (범용 구조)
```bash
git clone https://github.com/cursor/plugins
# 각 플러그인 디렉터리의 README 참고
```

## 사용법
플러그인별 사용법이 다르므로 각 디렉터리의 문서를 확인하세요.

## opencode 연동
Cursor 플러그인은 Cursor 전용이므로 opencode에 직접 이식되지는 않습니다.
다만 **MCP 서버 형태**로 제공되는 플러그인은 opencode에서 그대로 사용할 수 있습니다.
```json
{
  "mcp": {
    "some-plugin": { "type": "local", "command": ["npx", "-y", "<package>"], "enabled": true }
  }
}
```

## 링크
- https://github.com/cursor/plugins
- https://cursor.com

# Notion

## 개요
노트·문서·위키·데이터베이스·프로젝트 관리를 하나로 합친 **협업 워크스페이스 SaaS**입니다.
AI 기능이 내장되어 있습니다.

- 사이트: https://www.notion.so

## 설치 / 사용
- 웹(`notion.so`) + 데스크톱(Windows/macOS) + 모바일 앱
- 계정 생성 → 페이지/데이터베이스 생성
- 무료 플랜 제공

## API / 연동
- Notion API(Integration Token)로 페이지/DB를 읽고 씁니다.
- Notion **MCP** 서버(공식/커뮤니티)로 에이전트가 문서를 조회·작성할 수 있습니다.

## opencode 연동
Notion MCP를 opencode에 등록:
```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "notion": {
      "type": "local",
      "command": ["npx", "-y", "@notionhq/notion-mcp-server"],
      "enabled": true,
      "environment": { "NOTION_TOKEN": "{env:NOTION_TOKEN}" }
    }
  }
}
```
```
"이번 주 작업 내용을 Notion 데이터베이스에 정리해서 추가해줘"
```

## 링크
- https://www.notion.so
- https://developers.notion.com

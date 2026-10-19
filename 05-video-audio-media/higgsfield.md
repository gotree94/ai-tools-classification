# Higgsfield

## 개요
텍스트/참조로 이미지·영상·보이스 콘텐츠를 생성하는 **AI 네이티브 크리에이티브 스위트**입니다.
Sora 2, Kling 3.0, Veo 3.1, Seedance 2.5 등 30개 이상의 모델과 페이스 스왑·가상 피팅·
시네마 스튜디오·AI 에이전트 등 40개 이상의 도구를 제공합니다. 웹/모바일 지원.

- 사이트: https://higgsfield.ai
- MCP: https://higgsfield.ai/mcp
- Genjutsu API: https://open.higgsfield.ai

## 설치
웹 기반 SaaS로 **별도 설치가 없습니다**. Claude용 **MCP**와 **Genjutsu API**를 제공합니다.

## 사용법
1. 사이트 가입
2. 프롬프트/이미지 업로드
3. 모델·프리셋 선택
4. 생성

## opencode 연동
공식 **MCP 엔드포인트**를 opencode에 remote MCP로 등록할 수 있습니다.

```json
{
  "mcp": {
    "higgsfield": {
      "type": "remote",
      "url": "https://higgsfield.ai/mcp",
      "enabled": true,
      "headers": { "Authorization": "Bearer {env:HIGGSFIELD_API_KEY}" }
    }
  }
}
```

## 링크
- https://higgsfield.ai

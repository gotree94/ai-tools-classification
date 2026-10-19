# Vercel

## 개요
프론트엔드/풀스택 앱 **배포·호스팅 플랫폼**입니다. Next.js 개발사이며, Git 연동 자동 배포·
Edge/CDN·서버리스 기능을 제공합니다.

- 사이트: https://vercel.com

## 설치 / 사용
```bash
npm i -g vercel
vercel            # 로그인/프로젝트 연결 & 프리뷰 배포
vercel --prod     # 프로덕션 배포
```
웹 대시보드에서도 배포 가능. 무료(Hobby) 플랜 제공.

## opencode 연동
Vercel **MCP**(`vercel mcp`) 또는 CLI를 사용합니다.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "vercel": {
      "type": "local",
      "command": ["npx", "-y", "vercel", "mcp"],
      "enabled": true
    }
  }
}
```
```
"현재 브랜치를 프리뷰로 배포하고 로그를 요약해줘"
```

## 링크
- https://vercel.com
- https://vercel.com/docs

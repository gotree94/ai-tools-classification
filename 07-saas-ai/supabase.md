# Supabase

## 개요
**Postgres 기반 오픈소스 Firebase 대안(BaaS)** 입니다. DB·Auth·Storage·Edge Functions·Realtime을
제공합니다.

- 사이트: https://supabase.com

## 설치 / 로컬 개발
```bash
npm install supabase --save-dev
npx supabase init
npx supabase start            # 로컬 스택 (Docker 필요)
npx supabase functions serve
```
클라우드는 `supabase.com` 대시보드를 사용합니다.

## 사용법
- 프로젝트 생성 → 연결 문자열/키 발급
- `supabase db push`, `supabase functions deploy`로 스키마·함수 배포

## opencode 연동
Supabase **MCP** 또는 CLI를 사용합니다.

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "supabase": {
      "type": "local",
      "command": ["npx", "-y", "@supabase/mcp-server-supabase@latest",
                  "--read-only", "--project-ref", "{env:SUPABASE_PROJECT_REF}"],
      "enabled": true,
      "environment": { "SUPABASE_ACCESS_TOKEN": "{env:SUPABASE_ACCESS_TOKEN}" }
    }
  }
}
```
```
"users 테이블 스키마를 조회하고 RLS 정책을 추가해줘"
```

## 링크
- https://supabase.com
- https://supabase.com/docs

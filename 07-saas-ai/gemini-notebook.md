# Gemini Notebook (구 NotebookLM)

## 개요
업로드한 소스에 **근거(grounding)해 답하는** Google의 AI 리서치·학습 어시스턴트입니다.
PDF·Docs·Slides·YouTube·오디오 등을 소스로 요약·채팅·Audio/Video Overview·마인드맵·플래시카드를
생성합니다. **2026년 7월 NotebookLM → Gemini Notebook으로 개명**(동일 제품).

- 사이트: https://notebook.google.com

## 설치 / 사용
- 웹(`notebook.google.com`) + Gemini 앱 → **별도 설치 불필요**
- 소스 업로드 → 질문 / 생성

### 소스 제한
- 소스당 최대 50만 단어 또는 200MB
- 플랜별 노트북당 소스 수: Free 50 / Plus 100 / Pro 300 / Ultra 600
- 기업용: Gemini Notebook Enterprise (Google Cloud)

## opencode 연동
공개 API/MCP가 제한적이라 자동 연동은 어렵습니다. 자료 정리는 웹에서 하고,
그 결과물(요약 텍스트 등)을 파일로 내보내 opencode 작업에 참고하는 방식을 권장합니다.

```
(웹에서 요약 → summary.md 저장) → opencode에서 "summary.md 기반으로 초안 작성해줘"
```

## 링크
- https://notebook.google.com
- https://cloud.google.com/gemini-notebook

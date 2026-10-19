# Archify *(확인 필요)*

## 개요
**아키텍처 다이어그램** 생성 스킬로 보입니다. 10종 다이어그램 타입과 "Architecture Delta"
(변경분 표현)를 지원하며, 스킬 구조는 루트의 `archify/SKILL.md`입니다.
skills.sh 설치 수 130K+ 로 활발합니다. 한국어 README(`README_KO.md`)와 `meta.locale: "ko"`를 제공합니다.

- 저장소: https://github.com/tt-a1i/archify

## 설치

### 스킬 단독 설치
```bash
npx skills add tt-a1i/archify
```

### Claude Code 플러그인
```bash
/plugin marketplace add tt-a1i/archify
/plugin install archify
```

## 사용법
```
"이 모노레포의 아키텍처 다이어그램을 그려줘"
"지난 커밋 대비 아키텍처 변경분(delta)을 시각화해줘"
```

## opencode 연동
한국어 지원 스킬이므로 `SKILL.md`를 전역 스킬로 복사하면 한국어 환경에서 특히 유용합니다.
```bash
xcopy /E /I <repo>\archify %USERPROFILE%\.config\opencode\skills\archify
```

## 확인 필요
- 정확한 다이어그램 타입 목록과 출력 형식(HTML/SVG/PNG)은 저장소 README에서 확인하세요.

## 링크
- https://github.com/tt-a1i/archify

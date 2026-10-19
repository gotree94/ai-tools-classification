# awesome-opus5-5-videos

## 개요
Claude Opus 5.5로 만든 바이럴 영상 모음과 **그 프롬프트를 함께 제공**하는 awesome 리스트입니다.
각 영상은 Claude에게 애니메이션을 코드(HTML/Canvas/SVG/Three.js)로 작성하게 만든 것입니다.
MIT, 약 6,600 ★. `skillry.dev`에서 원본 vs 라이브 리메이크 418개를 비교 제공합니다.

- 저장소: https://github.com/yihui-dev/awesome-opus5-5-videos

## 설치
별도 설치가 없습니다(리포지토리 clone/열람).
```bash
git clone https://github.com/yihui-dev/awesome-opus5-5-videos.git
```

## 사용법
- `prompts/` 디렉터리와 `data/videos.json`의 프롬프트(703개)를 확인
- 원하는 프롬프트 복사 → 본인 에이전트(Claude, **opencode**)에 붙여 실행

### 카테고리
Motion graphics(58), Explainers(16), 3D scenes(14), Games & interactive(12)

## opencode 연동
프롬프트를 그대로 opencode에 붙여 실행하면 됩니다. 반복 사용하는 프롬프트는
커맨드 파일로 저장해 재사용할 수 있습니다.

`.opencode/command/anim.md`:
```markdown
---
description: HTML/Canvas 애니메이션 생성
---
다음 프롬프트의 애니메이션을 단일 HTML 파일로 구현해줘: $ARGUMENTS
```
```
/anim 파티클로 이루어진 유동적인 로고 인트로
```

## 링크
- https://github.com/yihui-dev/awesome-opus5-5-videos
- https://skillry.dev

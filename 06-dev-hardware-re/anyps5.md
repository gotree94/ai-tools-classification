# AnyPS5 *(성격이 달라 "기타"로 분류 가능)*

## 개요
PS5 실행 파일을 **Linux/Windows로 자동 포팅**하는 도구입니다. 에뮬레이션 없이 relinker로
타깃 OS 네이티브 포맷으로 변환하고, 동적 링킹용 시스템 prx 라이브러리 구현 + SPIR-V 셰이더
재컴파일러를 포함합니다. GPL-2.0.

- 저장소: https://github.com/boykopovar/AnyPS5
- 웹 변환기: https://boykopovar.github.io/AnyPS5

## 설치 / 빌드
C++/CMake 프로젝트입니다. `docs/dev/BUILD.md` 참고.

```bash
git clone https://github.com/boykopovar/AnyPS5
cd AnyPS5
# CMake로 빌드 (relinker-only 빌드는 macOS/Apple silicon에서도 동작)
```
사용법: `docs/user/USAGE.md`

## 사용법
PS5 실행 파일을 relinker로 변환 → 타깃 시스템 네이티브 실행.
SDL 게임패드 지원, 키보드/마우스는 `anyps5-input.ini`로 매핑합니다.

## opencode 연동
빌드/변환 명령을 셸 도구로 호출하는 정도입니다. 에이전트 특화 통합은 없습니다.
```
"AnyPS5 빌드 가이드대로 relinker를 빌드해줘"
```

## 분류 메모
다른 항목(에이전트·개발 도구)과 성격이 달라 **"기타(10-misc)"** 로 옮겨도 됩니다.

## 링크
- https://github.com/boykopovar/AnyPS5

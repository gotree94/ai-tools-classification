# RAD Debugger

## 개요
**Epic Games**가 만든 네이티브·유저모드·멀티프로세스 **그래픽 디버거**입니다.
로컬 x64(Windows/Linux) 대상을 지원합니다(ALPHA 단계). 자체 RDI 디버그 포맷과 RAD Linker를
포함합니다. MIT.

- 저장소: https://github.com/EpicGames/raddebugger

## 설치 (소스 빌드)

### Windows
1. MSVC Build Tools + Windows SDK 설치
2. `x64 Native Tools Command Prompt`에서:
   ```
   build
   build release
   ```

### Linux
```bash
sudo apt install build-essential libfreetype6-dev libx11-dev libxext-dev \
  libxfixes-dev libxrandr-dev libgl-dev libegl-dev
./build.sh
./build.sh release
```

사전 빌드 바이너리는 GitHub Releases에서 다운로드 가능.

## 사용법
- 실행: `build/raddbg.exe`(Win) / `build/raddbg`(Linux) → 로컬 프로세스 디버깅
- RAD Linker: `build radlink release`
- `radbin` 유틸: `build radbin release`

## opencode 연동
GUI 디버거이므로 opencode에서 직접 제어하기보다는, 빌드/실행 명령을 셸 도구로 호출합니다.
```
"RAD Debugger 디버그 빌드를 만들어줘"
```

## 링크
- https://github.com/EpicGames/raddebugger
- https://raddebugger.com

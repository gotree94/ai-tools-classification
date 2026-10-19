# CLI-Anything

## 개요
GUI 애플리케이션을 **CLI처럼 제어**할 수 있게 해주는 도구입니다. 에이전트가 직접 조작하기
어려운 GUI 앱(GIMP 등)을 커맨드로 다루게 합니다.

- 저장소: https://github.com/HKUDS/CLI-Anything

## 설치

### Claude Code
```
/plugin marketplace add HKUDS/CLI-Anything
/plugin install cli-anything
```

### Cursor
```bash
git clone https://github.com/HKUDS/CLI-Anything
bash cursor-plugin/scripts/install.sh
```

### opencode
opencode에는 **commands 복사 방식**으로 연동합니다.
```bash
git clone https://github.com/HKUDS/CLI-Anything
xcopy /E /I CLI-Anything\commands %USERPROFILE%\.config\opencode\command
```

## 사용법
```
/cli-anything ./gimp        # GUI 앱을 CLI 모드로 실행/제어
"이 이미지를 GIMP로 처리해줘 (CLI-Anything 사용)"
```

## 링크
- https://github.com/HKUDS/CLI-Anything

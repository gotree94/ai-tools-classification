# Agent-Reach

## 개요
에이전트에게 **인터넷 접근(웹 리서치) 능력**을 부여하는 도구입니다. 웹 검색·페이지 수집
등을 에이전트 워크플로에 통합합니다.

- 저장소: https://github.com/Panniantong/Agent-Reach

## 설치

### 원라인 설치
에이전트에게 아래처럼 요청하면 저장소의 `install.md` 지침대로 설치됩니다.
```
帮我安装 https://github.com/Panniantong/Agent-Reach 에 있는 install.md 를 따라서 설치해줘
```

### CLI
```bash
agent-reach install --env=auto
```
> `--env=auto`는 **기본이 read-only 점검**입니다. 실제 시스템 변경이나 `SKILL.md` 등록은
> `--system` 플래그를 명시해야 수행됩니다.

```bash
agent-reach install --env=auto --system
```

### 제거
```bash
agent-reach uninstall --dry-run      # 미리보기
agent-reach uninstall --keep-config  # 설정 유지
agent-reach uninstall
```

## 사용법
설치 후 에이전트가 웹 검색·페이지 fetch가 필요할 때 자동으로 활용합니다.
```
"최신 React 20 릴리스 정보를 인터넷에서 찾아 요약해줘"
```

## opencode 연동
설치 과정에서 `SKILL.md`가 등록되면 `~/.claude/skills/`에 배치될 수 있고, opencode가 이를
자동 인식합니다. 아니라면 해당 스킬 폴더를 `~/.config/opencode/skills/`로 복사하세요.

## 링크
- https://github.com/Panniantong/Agent-Reach

# Diagram Design

## 개요
**다이어그램(도식) 생성** 전용 스킬입니다. 흐름도, 구조도, 아키텍처 다이어그램 등을
에이전트가 만들도록 돕습니다.

- 저장소: https://github.com/cathrynlavery/diagram-design

## 설치

### 스킬 단독 설치
```bash
npx skills add cathrynlavery/diagram-design
```

> 주의: 스킬만 단독 설치하면 `/export-diagram` 같은 **슬래시 커맨드는 빠집니다**.
> 커맨드까지 쓰려면 플러그인(마켓플레이스) 설치를 사용하세요.

### Claude Code 플러그인
```bash
/plugin marketplace add cathrynlavery/diagram-design
/plugin install diagram-design
```

## 사용법
```
/export-diagram        # 다이어그램 내보내기
"이 시스템 구성도 다이어그램을 그려줘"
```

템플릿으로 직접 시작:
```bash
cp <repo>/template*.html ./my-diagram.html
```

## 갱신
```bash
npx skills update diagram-design
```

## opencode 연동
스킬 폴더(`SKILL.md`)와 커맨드 파일을 각각 복사합니다.
```bash
xcopy /E /I <repo>\skills\diagram-design %USERPROFILE%\.config\opencode\skills\diagram-design
xcopy /E /I <repo>\command %USERPROFILE%\.config\opencode\command
```

## 링크
- https://github.com/cathrynlavery/diagram-design

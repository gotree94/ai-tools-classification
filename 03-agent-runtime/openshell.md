# OpenShell (NVIDIA)

## 개요
NVIDIA가 만든 **자율 AI 에이전트용 안전·프라이빗 런타임**입니다. 커널 수준 격리 샌드박스에서
파일·시스템콜·네트워크 접근을 정책으로 강제 집행하고, 정책 변경 전 형식 검증으로 위험 접근을
사전 차단합니다. 에이전트는 실제 자격증명을 보지 못합니다. (약 16,700 ★)

- 저장소: https://github.com/NVIDIA/OpenShell

## 요구 사항
Linux, macOS(Apple Silicon), Windows **WSL2** + Docker/Podman

## 설치
```bash
curl -LsSf https://raw.githubusercontent.com/NVIDIA/OpenShell/main/install.sh | sh
openshell sandbox create --name demo
```

## 사용법
```bash
openshell sandbox create --name demo
```
문서의 "Run Your First Agent"에서는 **opencode**를 무료 OpenRouter 모델로 실행하고,
에이전트가 새 접근을 요청할 때 정책을 승인하는 흐름을 시연합니다.

## 연동
- CLI + 로컬 게이트웨이(컨트롤 플레인) + SDK(Python/TS/Go/Rust)
- **에이전트 스킬**: 코딩 에이전트가 OpenShell CLI·정책 작성법을 학습
  ```bash
  npx skills add NVIDIA/OpenShell
  ```
- Kubernetes(Helm) 배포 지원

## opencode 연동
샌드박스 내부에서 opencode를 실행하는 것이 기본 패턴입니다. OpenShell 정책으로 opencode의
파일·네트워크 접근을 통제할 수 있습니다.

## 링크
- https://github.com/NVIDIA/OpenShell

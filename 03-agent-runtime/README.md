# 3. 에이전트 실행 환경 / 인프라 / 브라우저

에이전트를 실행·격리·병렬화·라우팅하는 런타임 및 인프라 도구입니다.
*(목록에서 "확인 필요"로 표시된 항목은 조사 결과 모두 정상 저장소로 확인되었습니다.)*

## 도구 목록

| 도구 | 한 줄 요약 | 문서 |
|---|---|---|
| moli | AI 에이전트용 경량 헤드리스 브라우저(Rust) | [moli.md](./moli.md) |
| DeepSeek Harness (DSH) | 플러그인 기반 에이전트 런타임 + Web UI | [deepseek-harness.md](./deepseek-harness.md) |
| OpenRig | 멀티 에이전트 팀 오케스트레이션(tmux) | [openrig.md](./openrig.md) |
| OpenShell | NVIDIA의 에이전트 안전 샌드박스 런타임 | [openshell.md](./openshell.md) |
| OmniRoute | 375+ 프로바이더 AI 게이트웨이/라우터 | [omniroute.md](./omniroute.md) |
| Orca | 병렬 에이전트 데스크톱 오케스트레이터 | [orca.md](./orca.md) |
| DSH Desktop | DeepSeek Harness용 데스크톱 클라이언트 | [dsh-desktop.md](./dsh-desktop.md) |
| Ponytail | "게으른 시니어" 사고방식 프롬프트 스킬 | [ponytail.md](./ponytail.md) |

## opencode 연동 요약
- **OmniRoute**: OpenAI 호환 Base URL을 opencode provider로 등록하면 바로 사용 가능.
- **OpenShell**: 공식 문서에서 opencode를 샌드박스 내부 에이전트로 실행하는 예시를 제공.
- **OpenRig / Orca**: opencode를 실행 대상 에이전트로 지정 가능.
- **Ponytail**: 스킬(`SKILL.md`)·`AGENTS.md` 형태로 opencode에 적용 가능.
- 자세한 내용은 [../OPENCODE.md](../OPENCODE.md) 참고.

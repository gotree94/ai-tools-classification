# text-to-cad

## 개요
에이전트에 **CAD 능력**을 부여하는 플러그인/스킬입니다. 자연어·이미지로 STEP/GLB/STL/3MF
3D 모델을 생성하고, 제조(DFM/DfAM) 검사·엔지니어링 도면·3D 프린팅/판금/CNC 서비스를 연동합니다.
MIT, build123d + OpenCASCADE 기반.

- 저장소: https://github.com/earthtojake/text-to-cad
- 홈: https://texttocad.dev

> 주의: 요청 목록의 `OpenBMB/Text2CAD`는 404입니다. 연구용 `SadilKhan/Text2CAD`(NeurIPS'24)는
> 별개 프로젝트입니다. 실사용 도구는 `earthtojake/text-to-cad`입니다.

## 설치

### 에이전트에게 설치 요청
```
Install text-to-cad from https://github.com/earthtojake/text-to-cad
```

### CLI (local server / MCP)
```bash
cadgen mcp
cadgen doctor
uvx cadgen telemetry off   # 텔레메트리 끄기
```

### ⚠️ Windows 주의
Windows 11 **Smart App Control**이 켜져 있으면 unsigned OCP 모듈이 차단되어
`ImportError: DLL load failed`가 발생합니다. 끄거나 예외 처리하세요.

## 사용법
CAD 플러그인 설치 후 에이전트에게 요청:
```
"M5 볼트 4개가 있는 100×60mm 마운팅 브래킷을 설계해줘"
```
STEP이 주 산출물이며 STL/GLB/3MF가 부가 출력됩니다.

## opencode 연동
에이전트 스킬 형태이므로 `SKILL.md`를 opencode 스킬 경로로 복사하거나 `cadgen mcp`를 등록합니다.
```bash
xcopy /E /I <skill-dir> %USERPROFILE%\.config\opencode\skills\text-to-cad
```

## 링크
- https://github.com/earthtojake/text-to-cad
- https://texttocad.dev

# DSH Desktop *(확인 필요 → 정상 확인됨)*

## 개요
**DeepSeek Harness(DSH)용 커뮤니티 데스크톱 클라이언트**(Windows/macOS)입니다.
DSH의 로컬 Web UI·Host·플러그인 시스템을 네이티브 앱으로 감싸며, "데스크톱 자체도 플러그인"
원칙을 따릅니다. DeepSeek와 **공식 관계 없는 독립 커뮤니티 프로젝트**입니다(특정 버전 fork 고정).

- 저장소: https://github.com/anywhere-labs/dsh-desktop
- 다운로드: https://dshdesktop.cn

## 설치
- Windows x64: NSIS 설치 파일
- macOS Universal: DMG를 Applications로 드래그
- Node.js 설치 불필요(앱이 자동 관리)

## 사용법
1. 앱 실행 → **Setup Wizard**(창 모드·플러그인 시장·알림·Web 접근 범위 설정)
2. 내장 Harness Web UI 사용
3. 모바일 원격 제어(iOS/Android, 2.0.9+ 내장), 플러그인 마켓 내장

### 개발 빌드
```bash
git submodule update --init --recursive
corepack yarn install --immutable
corepack yarn dev
```

## 연동
- DSH 플러그인(`dsh-plugin-desktop`) — 데스크톱 셸(창·트레이·터미널·업데이트)이 플러그인으로 조합
- 플러그인 마켓·커뮤니티 에코시스템(4,120개 플러그인 디렉터리 등)

## opencode 연동
DSH 생태계는 `.claude/`·`AGENTS.md` 규약을 지원하므로, 공통 규약 파일을 공유해 지침을 통일할
수 있습니다. 직접적인 opencode 통합은 제공되지 않습니다.

## 링크
- https://github.com/anywhere-labs/dsh-desktop
- https://dshdesktop.cn

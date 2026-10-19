# MoneyPrinterTurbo

## 개요
주제/키워드만 주면 AI가 스크립트 작성 → 소재 매칭 → 자막·배경음악 생성 → 고화질 **숏폼 영상**
합성까지 자동화하는 원스톱 도구입니다. Python 3.11+, MIT, 매우 인기(약 133,000 ★).

- 저장소: https://github.com/harry0703/MoneyPrinterTurbo

## 설치

### pip 공식 패키지 (`mpt`, PyPI) — Windows
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install mpt
mpt webui
```

### Docker (권장)
```bash
git clone https://github.com/harry0703/MoneyPrinterTurbo.git
cd MoneyPrinterTurbo
docker compose -f docker-compose.release.yml up
```
- WebUI: `http://127.0.0.1:8501`
- API 문서: `http://127.0.0.1:8080/docs`

### uv 소스 배포
```bash
uv python install 3.11
uv sync --frozen
# Windows: webui.bat   |  macOS/Linux: sh webui.sh
```

그 외 Windows 원클릭 패키지(`update.bat` → `start.bat`), Google Colab 노트북 제공.

## 사용법
- **WebUI**: 주제 입력 후 생성. 첫 실행 시 `config.toml` 자동 생성 → API Key 입력
- **CLI**:
  ```bash
  uv run python cli.py --video-subject "人工智能如何改变日常生活"
  python cli.py --help
  ```
- **API**: `uv run python main.py` → FastAPI 서버

출력 포맷 9:16(1080×1920)/16:9/1:1, Edge TTS 무료 기본 지원, Whisper 자막, Pexels/Pixabay 소재.

## opencode 연동
CLI/서버 기반이므로 opencode에서 셸 도구나 스크립트로 호출합니다.
```bash
opencode 실행 후: "MoneyPrinterTurbo CLI로 'AI 트렌드' 숏폼 만들어줘"
```

## 링크
- https://github.com/harry0703/MoneyPrinterTurbo

# watermarks-remover

## 개요
**본인이 소유한 콘텐츠**에서 여러 벤더(Claude, Gemini/SynthID, OpenAI, open-LLM)의 AI
출처/워터마크를 제거하는 프라이버시 우선 도구입니다. 텍스트의 보이지 않는 유니코드·통계적
워터마크와 이미지/문서의 C2PA/EXIF/XMP 메타데이터를 처리합니다. MIT.

- 저장소: https://github.com/guillaumemeyer/watermarks-remover

## 설치

### 에이전트 스킬
```bash
python3 install_skill.py --skill remove-ai-marks --target claude-code
# Windows: py install_skill.py --skill remove-ai-marks --target claude-code
```
타겟: `claude-code`, `claude-project`, `codex`, `cursor`, `cowork` 등

### Claude Code 플러그인
```
/plugin marketplace add guillaumemeyer/watermarks-remover
/plugin install watermarks-remover@watermarks-remover
```

### 서비스 실행 (코어, Python 3.10+ stdlib만 필요)
```bash
make serve
# 또는
python3 service/scripts/server.py --host 127.0.0.1 --port 8765
```

### Docker
```bash
make docker-core-build
docker run --rm -p 127.0.0.1:8765:8765 watermarks-remover
```

## 사용법
```bash
SCRIPTS=service/scripts
python3 "$SCRIPTS/inspect_file.py" draft.md
python3 "$SCRIPTS/clean_file.py" draft.md -o draft.cleaned.md
python3 "$SCRIPTS/clean_file.py" photo.png -o photo.cleaned.png
```

### HTTP
- `POST /inspect`
- `POST /clean`
```bash
curl -X POST $WM/clean ...
```

> 텍스트의 Layer B 정리는 rewrite 백엔드(paraphrase/mlm) 설정이 필요합니다.
> 이미지/컨테이너 메타데이터 정리는 기본 동작입니다.

## opencode 연동
`remove-ai-marks` 스킬을 opencode 스킬 경로로 복사하거나, CLI 스크립트를 셸 도구로 호출합니다.
```bash
xcopy /E /I <skill-dir>\remove-ai-marks %USERPROFILE%\.config\opencode\skills\remove-ai-marks
```

## 링크
- https://github.com/guillaumemeyer/watermarks-remover

# 사이버캠퍼스와 웹 UI · 정재현

LMS 수집·전처리·평가 코드와 FastAPI/WebSocket UI입니다.

작업 디렉토리: `components/cybercampus`. 별도 가상환경에서 의존성을 설치하세요.

```bash
python -m pip install -r requirements.txt
python cnu/collect.py
python cnu/preprocess.py
python cnu/test_finetuned.py
```

수집은 로컬 `.env`의 Google API 키·학내 계정과 브라우저가 필요하며, 평가에는 별도 학습 데이터·모델 서버가 필요합니다. 업로드를 수행하는 태스크는 실행 전 자신의 테스트 파일과 계정을 설정해야 합니다. 실제 학내 시스템에 제출/변경을 일으킬 수 있으므로 태스크 내용을 먼저 확인하세요.

UI는 `cnu/ui/backend`에서 실행합니다. 해당 작업 디렉토리의 로컬 `.env`에 `GEMINI_API_KEY`와 Fernet 형식의 `APP_SECRET_KEY`를 설정하세요. 예를 들어 `python -c "from cryptography.fernet import Fernet; print(Fernet.generate_key().decode())"`로 로컬 키를 만들 수 있습니다.

```bash
cd cnu/ui/backend
uvicorn main:app --host 127.0.0.1 --port 8000
```

계정 DB와 자격증명은 로컬 `data/`에 생성되며 Git에서 제외됩니다.

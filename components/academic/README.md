# 통합정보시스템 · 박경서

통합정보시스템 궤적 수집·전처리·모델 평가와 FAQ RAG 코드입니다. FAQ 자료의 기준 시점을 확인해 사용하세요.

작업 디렉토리: `components/academic`. `pyproject.toml`은 Python 3.13 이상을 요구합니다.

```bash
uv venv --python 3.13
uv pip install -r requirements.txt
uv pip install -r rag/requirements_rag.txt
```

`collect.py`, `collect_te.py`는 로컬 `.env`와 모델 서버, 학내 로그인 환경을 확인한 뒤 실행합니다. 실제 사용 키 이름은 각 파일의 `os.getenv` 설정을 따르세요. `VLLM_BASE_URL`의 기본값은 `http://localhost:8000/v1`이며 서버가 제공하는 모델명과 맞춰야 합니다. `preprocess.py`, `preprocess_te.py`, `merge_data.py`는 먼저 준비한 궤적·데이터를 사용합니다. `rag/knowledge_base.py`와 `rag/retriever.py`에서 인덱스 생성/검색 흐름을 확인하세요.

# 학과 홈페이지 · 진민혁

학과 홈페이지 질문·궤적 수집·변환, 텍스트/VL LoRA 학습·병합·평가 코드입니다.

작업 디렉토리: `components/homepage`. 수집에는 `browser-use`, `python-dotenv`와 브라우저, Google API 키가 필요합니다. 학습에는 `torch`, `transformers`, `peft`, `accelerate`, `bitsandbytes`, `qwen-vl-utils` 등이 필요하며 GPU/드라이버에 맞춰 별도 환경을 구성하세요.

```bash
python homepage/homepage_collector.py 0 1
python homepage/homepage_convert.py
```

로컬 `.env`의 Google API 키를 사용합니다. 수집 출력은 `HOMEPAGE_DATA_DIR`(기본 `data/homepage`)이며 변환기는 해당 궤적을 읽습니다. `finetune.py`, `finetune_vl.py`, `merge.py`는 별도로 준비한 학습 데이터와 GPU를 요구합니다. VL 기본 모델은 `BASE_MODEL`로 지정할 수 있습니다.

`eval_runner.py`, `eval_runner_v2.py`는 모델별 설정 키가 다르므로 파일의 `MODEL_CONFIGS`와 `DOMAIN_CONFIGS`를 확인해 실행합니다. `QWEN_FT_MODEL_NAME`, `QWEN_*_BASE_URL`은 자신의 vLLM 서버가 제공하는 이름과 주소로 설정합니다. `eval_runner_v2.py`의 VL 기본 모델명은 `QWEN_VL_BASE_MODEL_NAME`으로 설정할 수 있습니다. Anthropic API를 사용하는 선택지는 `ANTHROPIC_API_KEY`를 요구합니다.

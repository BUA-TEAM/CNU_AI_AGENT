# 도서관 VL 파이프라인 · 박소윤

도서관 궤적 수집, 멀티모달 데이터 전처리, QLoRA 학습과 평가 코드입니다.

작업 디렉토리: `components/library`. 기존 requirements는 GPU 학습/추론 의존성까지 포함하므로 환경에 맞는 별도 가상환경을 사용합니다. 학습 추가 의존성은 `cnu-finetune/requirements_finetune.txt`에 있습니다.

```bash
python -m pip install -r requirements.txt
cd browser-use
python collect_train_vl.py --model gemini 0 1
python preprocess_vl.py --help
```

수집에는 로컬 `.env`의 Google API 키와 `CNU_ID`, `CNU_PASSWORD`, 브라우저가 필요합니다. 입력·출력 디렉토리를 확인하세요. GPU 학습은 `cnu-finetune`에서 `python finetune_vl.py`로 실행하며 `LIBRARY_TRAIN_DATA`(기본 `../browser-use/data/ft_train_vl_gemini_v5.jsonl`)와 모델 가중치를 준비해야 합니다. 학습 데이터와 가중치는 포함하지 않습니다.

평가기는 `browser-use`에서 `python evaluate_finetuned_vl.py 0 1`로 실행합니다. 별도 vLLM 모델 서버와 로그인 환경이 필요합니다. 원본에 없는 증명서(cert) 태스크는 지원하지 않습니다.

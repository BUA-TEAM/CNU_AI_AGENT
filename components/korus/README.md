# KORUS 학습 구성요소 · 최민우

궤적의 SFT 데이터 변환, QLoRA 학습, 오프라인 평가와 MLX 도구입니다.

작업 디렉토리: `components/korus`, Python 3.11 이상.

```bash
uv sync --extra dev
uv run pytest -q
uv run python -m cnu_agent.data.trajectory_to_sft --in trajectories --out data
```

변환 입력은 `trajectories/<task_id>/steps.jsonl`이며 각 step에 `task_id`, `step`, `input_messages`(system과 user), `model_output`, 선택적 `screenshot_path`가 있어야 합니다. `--success-only`를 쓰면 `history.json`의 마지막 done.success도 필요합니다. 화면 파일은 궤적 디렉토리를 기준으로 읽습니다. task 단위로 train/eval을 나눕니다.

CUDA GPU에서 학습·오프라인 평가:

```bash
uv sync --extra training
uv run python -m cnu_agent.training.qlora_sft --train data/korus_train.jsonl --eval data/korus_eval.jsonl --out ckpt/korus-lora
uv run python -m cnu_agent.student.eval_offline --eval data/korus_eval.jsonl --adapter ckpt/korus-lora --out output/eval.json
```

기본 모델은 `Qwen/Qwen2.5-VL-32B-Instruct`이며 가중치 다운로드와 충분한 GPU 메모리가 필요합니다. Apple Silicon의 `chat_mlx.py`, `scripts/peft_to_mlx_adapter.py`는 `uv sync --extra mlx --extra browser`로 의존성을 설치하는 별도 보조 경로입니다.

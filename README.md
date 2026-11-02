# CNU AI Agent · BUA

충남대학교 캠퍼스 웹 업무를 대상으로 만든 Browser Use Agent(BUA) 팀 프로젝트입니다. 웹 작업 궤적의 수집·전처리·모델 학습·평가 코드와 사이버캠퍼스 UI로 구성됩니다.

| 구성요소 | 내용 |
| --- | --- |
| [KORUS](components/korus/README.md) | 궤적 → SFT 변환, QLoRA 학습, 오프라인 평가, MLX 도구 |
| [통합정보시스템](components/academic/README.md) | 태스크 수집·평가, 전처리, FAQ RAG |
| [도서관](components/library/README.md) | 시각 언어 모델용 궤적 수집·전처리·학습·평가 |
| [사이버캠퍼스와 UI](components/cybercampus/README.md) | LMS 수집·전처리·평가, FastAPI/WebSocket UI |
| [학과 홈페이지](components/homepage/README.md) | 홈페이지 질의·수집·변환, 모델 학습·병합·평가 |

## 실행

각 구성요소의 README에서 작업 디렉토리와 설치·실행 방법을 확인하세요. 구성요소별 가상환경을 사용하며 API 키·학내 계정은 로컬 `.env`에 설정합니다. 학습 데이터·모델 가중치는 별도로 준비해야 합니다. 학습에는 GPU가, 브라우저 실행에는 해당 시스템의 접근 권한이 필요합니다.

## 시연과 발표

- [데모 영상](https://youtu.be/LFE1g91TS28)
- [발표 영상](https://youtu.be/P-qoQXcvrM8)

## 출처

| 담당 | 원본 저장소 | 기준 커밋 |
| --- | --- | --- |
| 최민우 | [Sunkist18/cnu-ai-agent](https://github.com/Sunkist18/cnu-ai-agent) | [d12c952](https://github.com/Sunkist18/cnu-ai-agent/tree/d12c952dbbcb9292b06be88c032d8c788997d761) |
| 박경서 | [kyungseopark/BUA_project](https://github.com/kyungseopark/BUA_project) | [0dfeb6c](https://github.com/kyungseopark/BUA_project/tree/0dfeb6c9c296e353cc7e41752ce6689635cb64db) |
| 박소윤 | [soyun11/BUA-library](https://github.com/soyun11/BUA-library) | [89eb557](https://github.com/soyun11/BUA-library/tree/89eb557378a73efe56afcca5e13390f530a31b6d) |
| 정재현 | [jaehyun429/BUA](https://github.com/jaehyun429/BUA) | [0c5fe64](https://github.com/jaehyun429/BUA/tree/0c5fe642a079c2007a9e80bb85a6f125cc2952a0) |
| 진민혁 | [RangKoon/BUA](https://github.com/RangKoon/BUA) | [bcedfb3](https://github.com/RangKoon/BUA/tree/bcedfb3de70c352e8e2845f8799111b9a5222959) |

지도교수: 이영석.

도서관·사이버캠퍼스 원본 README의 라이선스 표기는 MIT입니다. 각 원본에 별도 LICENSE 파일은 없으므로 외부 재배포 시 원저자의 허락 범위를 확인하세요.

# ml-serving-api

이상탐지만으로는 부족하다. "다음 달 에너지 비용이 얼마나 오를지" 예측해서 API로 서빙하는 프로젝트

## 해결하는 문제

> energy-anomaly-pipeline에서 이상은 감지했는데
> "앞으로 얼마나 오를지"를 예측해서 의사결정에 쓸 수 있어야 함

## Stack

`Python` `FastAPI` `scikit-learn` `Docker` `uvicorn`

## Structure

- `app/main.py` — FastAPI /predict 엔드포인트
- `app/model.py` — 모델 로드 + 추론
- `app/schemas.py` — 요청/응답 스키마
- `models/` — 학습된 모델 파일 (.pkl)
- `notebooks/` — 모델 학습 과정
- `Dockerfile`
- `tests/`

## Features

| 기능 | 설명 | 상태 |
|------|------|------|
| 모델 학습 | scikit-learn 시계열 예측 + pickle 저장 | 예정 |
| API 서빙 | FastAPI /predict 엔드포인트 | 예정 |
| Docker | 컨테이너화 배포 | 예정 |
| API 문서 | Swagger UI 자동 생성 | 예정 |

## How to Run

```bash
pip install fastapi uvicorn scikit-learn
uvicorn app.main:app --reload
```

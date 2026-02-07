# Bike Sharing Demand Prediction 🚲

공공자전거 대여 수요를 예측하기 위해  
시간, 요일, 날씨 데이터를 분석하고 머신러닝 모델을 적용한 회귀 프로젝트입니다.  
Kaggle **Bike Sharing Demand** 데이터를 사용하였습니다.

---

## 📌 Project Overview
- 목표: 시간·날씨 기반 자전거 대여 수요 예측
- 접근 방법:
  - EDA를 통한 패턴 분석
  - Feature Engineering
  - 모델 비교 (Linear Regression → RandomForest)
- Kaggle Public Score: **0.47050**

---

## 📊 Dataset
- Source: Kaggle Bike Sharing Demand
- Train size: **10,886 rows**
- Test size: **6,493 rows**
- Target variable: `count` (자전거 대여 수)

---

## 🔍 EDA & Feature Engineering

### Time-based Analysis
- 주중에는 **7–8시**, **17–19시**에 뚜렷한 수요 피크 발생
- 주말에는 오전부터 점진적으로 증가하여 **13시**에 최대 수요 기록
- 출퇴근 수요와 레저 수요의 시간대 차이 확인

### Weather Analysis
- `weather` 변수는 표본 수 불균형으로 평균 왜곡 가능성 존재
- 이를 해결하기 위해:
  - `weather = 1,2` → 날씨 양호
  - `weather = 3,4` → 날씨 불량
- 새로운 변수 `weather_group` 생성

---

## 🤖 Modeling

### Baseline Model
- Linear Regression
- RMSE (validation): **141.05**

### Final Model
- RandomForestRegressor
- RMSE (validation): **39.04**
- Kaggle Public Score: **0.47050**

👉 비선형 모델이 시간·날씨 변수 간 상호작용을 효과적으로 학습하여  
기준선 모델 대비 성능을 크게 개선함.

---

## 📁 Project Structure
bike-sharing-demand/
├── README.md
├── bike_demand_analysis.ipynb
├── notebook/
│ └── README.md
└── submission/
├── README.md
└── submission.csv


##  Conclusion
EDA 기반 가설 설정과 feature engineering을 통해  
공공자전거 수요 예측 모델을 구축하였으며,  
모델 비교 및 Kaggle 제출을 통해 성능을 검증하였습니다.

본 프로젝트를 통해 데이터 분석 전 과정  
(문제 정의 → 분석 → 모델링 → 검증)을 경험하였습니다.


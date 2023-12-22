# 공공데이터를 활용한 흡연 여부 예측
![1](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/8a5047de-ed2d-4dec-9841-7c90d04e39f1)

## 요약
사람에게서 나타나는 생체 특성 중 흡연여부에 영향을 미치는 요인을 찾고자 하였다. 분석을 위해 분류 모델 중 나이브베이즈분류기, knn, 다항로지스틱회귀모형, 의사결정나무, 랜덤포레스트, XGBoost, SVM 총 7개의 모델을 사용하였다. 분석에 사용된 데이터는 국민건강보험공단에서 제공하는 건강검진정보 데이터를 사용하였다. 선행연구들을 바탕으로 분류모델의 학습에 있어 헤모글로빈수치(HMG), 간기능 수치(GAMMA_GTP), 신장 수치(CREATININE), 성별(SEX)이 흡연여부에 높은 영향성을 줄 것으로 예상하였다. 랜덤포레스트를 최종모델로 설정하여 분석한 결과 가설과 유사하게 변수중오도가 도출되었고 성별이 가증 큰 영향을 끼치는 것으로 확인되었다. 


## EDA
EDA를 통해서 다음과 같은 사실을 확인 할 수 있었다. 

- 여성의 경우 남성보다흡연자 비율이 적다.
- 나이대가 높아질수록 흡연자의 비율이 적어진다.
- 지역별 흡연율 차이는 성비에 기인하는데, 울산은 대표적인 남초도시이다. 이에 따라 흡연율이 높다. 
- 흡연자의 크레아티닌 수치가 높다.
- 음주자일수록 흡연율이 높다.
- 흡연자일수록 감마지피티(간수치)가 높다.
- 흡연자일수록 HDL이 낮다.

![2](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/243c4e68-d490-4ae9-88fd-cd15a9ea65ea)
![3](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/feb55ed9-e131-4a94-9cee-9cbe082ed100)
![4](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/764c861b-1d5f-4799-840f-13c6169cbfe1)

## 모델링
이번 프로젝트에서는 총 7가지의 모델을 사용 하였으며, 각 모델에 대해 최적의 하이퍼파라미터를 찾고 성능을 비교한 후 최종 모델을 선정했다. 

### 모델 성능 비교
![13](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/dffa2ea8-62a6-49c9-9419-b77f368d859a)

### 모델 소개
![6](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/df60c1af-076b-4e46-8d67-490f3ee03559)
![7](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/935e9f40-0929-460c-98f9-ed9e16f0e8f2)
![8](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/a3575e1e-3fa2-4fee-8d63-89a02a3c4ee1)
![9](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/4d89111e-b3a5-4dc8-a733-eb1b35c87a57)
![10](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/6dcaa77c-5467-4ac1-af73-6db0a25ffcc7)
![11](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/1ce4b770-95ce-40c2-bb1f-98f87a302567)
![12](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/986fcbb1-1362-4225-a93e-4554964e2dff)

## 최종 모델 및 성능 측정 
최종적으로 성능이 우수하며 속도가 빠르고 과적합에 효과적이고 해석이 용이한 랜덤포레스트가 선정되었다. 다음은 랜덤포레스트에 대한 변수중요도와 ROC CURVE 이다. 프로젝트 초반에 세웠던 가설과 동일하게 성별(SEX), 헤모글로빈(HNG), 간기능수치(GAMMA_GTP), 신장수치(CREATININE)이 변수중요도 상위에 위치함을 확인 할 수 있었다. 

![14](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/204c5be8-3c4d-4f03-8581-a21e5455eabc)
![15](https://github.com/dongwan97/Smoking-Prediction-Model/assets/122766043/a45dd32b-498b-4fd6-82a1-b402b3f39ea5)

## 결론
### 가설 확인
본 분석에서는 7개의 분류모델을 학습하는 과정을 거쳤고 모델의 성능, 해석의 용이성, 속도, 일반화가능성을 기준으로 랜덤포레스트를 흡연 분류 예측 최적 모형으로 선정하였다. 

분류모델의 학습에 있어 헤모글로빈수치(HMG), 간기능수치(GAMMA_GTP), 신장수치(CREATININE), 성별(SEX)가 흡연여부에 높은 영향성을 줄 것이라 가설을 세웠다. 실제 분석 결과 가설과 동일하게 높은 영향을 줌을 확인 할 수 있었다. 

### 활용방안
#### 1) 소비자 건강 헬스케어 앱
최근 우리은행에서는 디지털 헬스케어 기업 GC케어와 헬스케어 플랫폼 서비스를 출시했다. 이 서비스는 소비자의 건강도를 수치로 나타내어 사용자로 하여금 손쉽게 건강을 관리할 수 있도록 도와주는 서비스이다. 이번 프로젝트의 흡연 예측을 활용하면 사용자의 흡연여부를 예측하고 이를 기반으로 서비스 내에서 보다 정확한 건강 점수를 제공 할 수 있다. 또한 흡연여부를 예측하여 흡연,금연,비흡연, 사용자를 구분하고 그에 맞춤화 된 서비스를 제공 할 수있다.

#### 2) 금연 정책
금연정책을 시행할 때 대상을 정확히 타겟하여 맞춤형으로 금연정책을 시행하면 보다 높은 효과를 가질 수 있을 것이다. 또한 모든 성인을 대상으로 흡연전수조사를 하는데 한계점이 존재하므로 건강 데이터를 기반으로 성인의 흡연을 예측하고 그에 맞는 금연정책의 동향을 파악하고 의사결정의 근거로 활용하면 더 높은 효과를 가질거라 생각된다. 

# Codestates-Section2
# 1. 프로젝트 개요
 신규고객을 확보하는 일은 매우 중요한 일이다. 기존 고객 관리도 신규고객 관리만큼 중요한 일이다.<br>
 기존 고객을 이탈을 방지하고 유지할 수 있도록 고객 정보를 통해 고객 이탈을 예측하고, 이탈 할 것으로 예축되는 고객에게 막춤 관리 서비스를 지원 할 수 있고 나아가 이탈이 자주 발생하는 원인에 대한 보완을 할 수 있도록 프로젝트를 진행을 하였다.<br><br><br>

# 2. 데이터 
1) 데이터 출처 : 캐글 [https://www.kaggle.com/datasets/blastchar/telco-customer-churn] <br>
2) 데이터 설명 : Telco Systems[미국 통신 관련 서비스 기업] 고객 데이터, 지난달 이탈 고객 <br>
3) 데이터 크기 : 7043 x 21 <br> <br><br>

# 3. 데이터 분석 및 시각화
## 3-1. 가설1 : 젊을 수록 변화에 빠르게 적응할 것으로 예상하여 노년의 이탈률이 낮을 것이다. 또한 가족할인등으로 인해 가족단위로 같은 통신사를 쓸 것으로 보여서 싱글이 더 이탈하기 쉬울 것이다.

### 3-1-1. 검증 방법 : 카이제곱검증 & 이탈 비율 <br>

### 3-1-2. 결과 <br>
<img width="543" alt="image" src="https://user-images.githubusercontent.com/102211628/198220121-570889f5-4488-4ac9-b44b-9c6f4fe441c5.png">

- 가설처럼 배우와, 자녀가 있는 고객이 이탈률이 낮다. 

<img width="259" alt="image" src="https://user-images.githubusercontent.com/102211628/198220798-3b0f4f3c-636d-4c31-bbc6-1d19753154aa.png">

- 가설과 반대로, 노인의 이탈 비율이 더 높다. <br><br>

## 3-2. 가설2 : 서비스를 이용하는 고객일수록 이탈률이 적을 것이다.

### 3-2-1. 검증 방법 : 카이제곱검증 & 이탈 비율 <br>

### 3-2-2. 결과 <br>
<img width="518" alt="image" src="https://user-images.githubusercontent.com/102211628/198223728-057a7256-39a0-48db-a472-98c2c174eca1.png">

<img width="273" alt="image" src="https://user-images.githubusercontent.com/102211628/198227380-0152576b-bc3e-41e2-af88-283783315eac.png">

<img width="296" alt="image" src="https://user-images.githubusercontent.com/102211628/198227431-2d6af963-afae-4399-b2af-768d2829b9c1.png">

- 보안&기술 서비스는 서비스를 미사용 고객보다 서비스를 사용하는 고객이 이탈률이 낮다 하지만 스트르밍에서는 서비스를 사용하는 고객이 더 이탈을 많이 하는 것을 확인할 수 있다.<br><br>
## 3-3. 가입기간

### 3-3-1. 계약 유형 & 가입 기간 <br>
<img width="679" alt="image" src="https://user-images.githubusercontent.com/102211628/198229128-6489f614-ff46-460f-b797-b9f591797cc8.png">

- 계약 유형으로는 월계약 -> 1년 -> 2년 계약 순으로 이탈이 적다<br>
- 가입기간이 짧을수록 이탈비율이 높다.
### 3-3-2. 가입기관과 청구된 매달 금액 분석<br><br>
<img width="419" alt="image" src="https://user-images.githubusercontent.com/102211628/198229873-0fcf9e21-9713-4dfd-b659-ff19801b2178.png">

- 가입기간과 청구된 금액은 상관관계가 있으나, 아주 약한 상관관계이다.<br> <br>
## 3-4 분석 결과 
### 3-4-1 고객 개인 정보
- 배우자와 자녀가 았고, 년 단위로 계약하며, 장기고객일 수록 이탈을 적게 한다.
- 노인이 노인이 아닌 사람들보다 이탈 비율이 더 높다.
### 3-4-2 서비스 
- 보안, 기술 서비스 사용 고객은 미사용자 보다 이탈을 적게한다.
- 스트리밍 서비스를 가입한 고객이 이탈률이 높다. 
### 3-4-2 향후 서비스 개선점
- 노인 대상으로 서비스를 더 확대한다. 
-스트리밍 서비스 기술을 현재보다 더 발전시키고 보완하고, 스트리밍 서비스 요금 측정을 다시 조절해보도록 한다.<br><br><br>
# 4. 모델 
## 4-1. BaseModel

- 분류모델이므로 기준모델은 최빈값으로 결정
<img width="444" alt="image" src="https://user-images.githubusercontent.com/102211628/198232982-570459d7-624a-4b66-8979-50c87fdbbbd6.png">

## 4-2. 평가지표
- 불균형이 심한 데이터로 F1 score 선정
## 4-3. 모델 선정

<img width="593" alt="image" src="https://user-images.githubusercontent.com/102211628/198236958-b53cc258-f6e3-4ace-8a38-340af527b9d5.png">
<img width="685" alt="image" src="https://user-images.githubusercontent.com/102211628/198236842-91116070-ecec-49f6-9aa5-4f91f87ce18f.png">

- LogisticRegression, RandomForestClassifer를 비교하였을때, LogisticRegression, RandomForestClassifer 두 모델이 모두 기준모델보다 정확도 f1 score이 더 높다.<br>
- LogisticRegression, RandomForestClassifer 두 모델을 비교해보면 F1 score은  LogisticRegression 약 0.09 더 높게 나왔고, 정확도는 RandomForestClassifer 약 0.06 더 높게 나왔다. 평가지표를 F1 score로 하기로 결정하였기때문에 두 모델 중 LogisticRegression 모델의 하이퍼 파라미터튜닝르 진행함.<br>

- LogisticRegressin 모델의 하이퍼파라미터 튜닝 및 교차검증
  - Stratified K-Fold : 불균형한 분포도를 가진 레이블 데이터 집합을 위한 K-Fold 방식
  - Stratified K-Fold를 통한 교차검증[K=5]
## 4-4. 모델 결과
<img width="1088" alt="image" src="https://user-images.githubusercontent.com/102211628/198239209-ef259999-4edc-42e1-933d-5b3b31a1c7bd.png">

- 5번 교차검증 결과 2번 교차검증일 때, Accuracy : 0.763 / f1 score : 0.6454 가장 높게 나왔다. 이때 하이퍼파리미터는 C=0.01 .class_weight=‘balanced’,max_iter=300, n_jobs=-1, random_state=42

## 4-5. 최종 모델 해석
<img width="324" alt="image" src="https://user-images.githubusercontent.com/102211628/198241077-f3995d48-6975-4db1-802d-9dd651e908c0.png">
<img width="706" alt="image" src="https://user-images.githubusercontent.com/102211628/198241136-ddd64e52-9d21-4504-8b47-9febab045e3d.png">

- 컬럼별 중요도 순은 가임기간, 매달정구금액, 자녀 없음 순이다.
- 1D PDP로 보았을 때, tenure은 가입기간이 길어질 수록 이탈할 확률이 줄어든다는 것을 알 수 있다. 그리고 2D PDP에서는 tenure 7개월 이내일때, 월 요금(MonthlyCharges)이 101.32~118.2면 고객이 이탈할 확률이 80프로 이상으로 가장 높은 것을 알 수 있다. 또한 처음 가입했을 때, 월 요금이 약 25.75달러정도이면 이탈할 확률이 39프로 이고, 50.25달려면 이탈할 확률이 54프로로 많이 증가하는 것을 알 수 있다. 따라서 처음 가입하는 고객들에게 월 요금은 25달러 이하로 책정을 하게 된다면 고객 이탈 방지를 할 수 있을 것으로 예상된다. <br><br><br>

# 5. 프로젝트 개선방안 및 향후 기대효과 
## 5-1. 개선방안
- 데이터 불균형을 해결하기위해서 Under sampling, Over Sampling으로 모델 성능 개선
- 고객 가입 기간과 요금에 대한 추가 분석 진행
## 5-2. 향후 프로젝트에 대한 기대효과
- 기업의 고객 이탈을 분석하여, 서비스 측면에서 개선점과 기업의 앞으로의 방향을 잡는데 도음을 줄수 있음.
- 이탈 고객을 예측하여, 고객이 이탈을 결정하기전 지속적인 상담과 혜택을 먼저 권유하여 이탈을 방지할 수 있음.
- 이탈한 이유를 분석하여 신규 고객 확보에 활용 가능.













🍔 

# Is Your Burger Really Worth the Price?
This project aims to predict the fair price of "Patty Patty" (name of burger) from Pipit Burger in Seongsu, Seoul when the menu launches in the US 
성수동에 위치한 삐삣버거의 '패티패티' 메뉴가 미국 진출시 적정 가격을 예측하는 프로젝트

## Goal
The goal is to predict the fair price of the burger using linear regression models, based on nutrition facts, length of menu, brand power index and other features
영양성분, 메뉴 길이, 브랜드 파워 지수 등에 기반하여 버거의 적정 가격을 회귀 모델을 이용하여 예측

## Data Preprocessing
### Data Crawling
- Crawling
  Assuming ingredients and taste of every burger are indistinguishable, we crawled prices and nutrition facts of menus from nine well-known burger chain in the US
  모든 버거의 재료가 같고 맛도 동일하다는 가정하에 미국 내 유명 버거 체인점 9곳의 버거 가격, 영양성분을 크롤링해 데이터 생성

### Derived Variables
- Length of Menu
  Assumption : The longer the length of menu is, the more price rises
  메뉴 길이가 길 수록 가격이 높다고 가정하여 데이터에 추가
- Ratio of patty, cheese and bun 
  Assumption : 
  단순히 사이즈가 큰 버거가 아니라 빵은 작지만 패티와 치즈가 많은 버거를 비싼 것으로 가정
- 가격대별 범위 설정 Price Range
  - low(< IQR 25)
  - mid(< median)
  - high(< IQR 75)
  - extra_high(> IQR 75)

### External Data 
- Brand Power Index
  브랜드에 따른 가격 변화 추이를 보고자 매출액, 시장점유율, 점포수를 기반하여 변수 생성

## Modeling
- 아래의 모델들을 사용하여 모델링 진행
  - LinearRegression
  - DecisionTreeRegressor
  - RandomForestRegressor
  - GradientBoostingRegressor
  - XGBRegressor
- 가격대 별 데이터 균등 분할 후 모델링
  - 가격대 별로 데이터 쏠림 현상을 방지하기 위해 데이터 균등 분할 후 모델링

- RandomForestRegressor가 가장 높은 성능을 보임

## 결론
- RandomForestRegressor를 회귀 모델로 활용
- 메뉴 이름 : pipit double double burger from seongsu in South Korea
- 예측 버거 가격 : $ 8.05(환율 1,180원 적용시) - 9,500원
- 실제 버거 가격 : 9,500원
- 환율에 따라 가격 변동이 있겠지만 실제 가격과 비슷하게 예측했음

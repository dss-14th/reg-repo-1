🍔 

# Is Your Burger Really Worth the Price?
This project aims to predict the fair price of "Patty Patty" (name of burger) from Pipit Burger in Seongsu, Seoul if the menu launches in the US 

## Goal
The goal is to predict the fair price of the burger using linear regression models, based on nutrition facts, length of menu, brand power index and other features

## Data Preprocessing
### Data Crawling
- Crawling
  Assuming ingredients and taste of every burger are indistinguishable, we crawled prices and nutrition facts of menus from nine well-known burger chain in the US
  
### Derived Variables
- Length of Menu
  Assumption : The longer the length of menu is, the more price rises

- Proportion of patty, cheese and bun 
  Assumption : Expensive burger contains A LOT of cheese, patty, and a small bun

- Price Range
  - low(< IQR 25)
  - mid(< median)
  - high(< IQR 75)
  - extra_high(> IQR 75)

### External Data 
- Brand Power Index
  Calculated using sales, market share and units
  브랜드에 따른 가격 변화 추이를 보고자 매출액, 시장점유율, 점포수를 기반하여 변수 생성

## Modeling
- Following models were applied:
  - LinearRegression
  - DecisionTreeRegressor
  - RandomForestRegressor
  - GradientBoostingRegressor
  - XGBRegressor
- Splitting data evenly 
  - To prevent 
  - 가격대 별로 데이터 쏠림 현상을 방지하기 위해 데이터 균등 분할 후 모델링

- RandomForestRegressor performed the best

## Conclusion
- RandomForestRegressor was applied
- menu : pipit double double burger from seongsu in South Korea
- Estimated price : $ 8.05($1.00 = 1,180 won) - 9,500 won
- Actual price : 9,500 won
- Price may change based on exchange rate but prediction was well-made!

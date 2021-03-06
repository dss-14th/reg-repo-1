![pipit1](https://user-images.githubusercontent.com/68367358/96970355-8650b280-154e-11eb-819a-895c5b786d86.png)



# Is Your Burger Really Worth the Price?🍔 
This project aims to predict the fair price of "Patty Patty" (name of burger) from Pipit Burger in Seongsu, Seoul if the menu launches in the US 

## Goal
The goal is to predict the fair price of the burger using regression models, based on nutrition facts, length of menu, brand power index and other features

## Data Preprocessing
### Data Crawling
- Crawling
  Assuming ingredients and taste of every burger are indistinguishable, we crawled prices and nutrition facts of menus from nine well-known burger chain in the US
  (website : https://www.menuwithprice.com)
  
### Derived Variables
- Length of Menu
  - Assumption : The longer the length of menu is, the more price rises

- Proportion of patty, cheese and bun 
  - Assumption : Expensive burger contains A LOT of cheese, patty, and a small bun

- Price Range
  - low(< IQR 25)
  - mid(< median)
  - high(< IQR 75)
  - extra_high(> IQR 75)

### External Data 
- Brand Power Index
  - Calculated using sales and units
  
## Modeling
- Using data splited equally by price range for train and test.
- Following models were applied:
  - LinearRegression
  - DecisionTreeRegressor
  - RandomForestRegressor
  - GradientBoostingRegressor
  - XGBRegressor
- DecisionTreeRegressor performed the best considering of RMSE($) and r_squared score.
![Screen Shot 2020-10-24 at 17 53 47](https://user-images.githubusercontent.com/68367134/97077830-d9476a00-1621-11eb-9112-a746dfd2a851.png)

## Conclusion
- DecisionTreeRegressor was applied
- Menu : pipit double double burger from seongsu in South Korea (length - 9)
- Actual price in Korea: 9,500 won ($ 8.05 ($1.00 = 1,180 won))
- The model shows that $ 4.82 is a reasonable price when entering American burger industry.
- Price may change based on exchange rate but prediction was well-made!

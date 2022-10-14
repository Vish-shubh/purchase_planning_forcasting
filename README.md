# Building a purchase planning process on the basis of forecasting visitor visiting the restaurant

# Aim:to predict the how many visitors, visit each restaurant Forecasting helps in effective planning for purchase of ingredients and scheduling of staffs

Objective:
focus on guest satisfaction, profitability, management on Staff scheduling, inventory management, menu analysis

How data collected:
We can collect the data from Yelp and Square API so data is generally in JSON format we are download the JSON file. Read the JSON file and perform the further operation around 10 GB data available so there is no need to find the restaurant visitor data.
How much data (row/Column):
600K rows and * 35 column

Numeric feature was around 24 and categorical feature are around 11
Total size of Data in MB and GB 
1.2GB – 3.5GB

Preprocessing steps are performed:
- check properties: shape, info, isna.
- data type format change: Time series data was object form so we change and convert date time format
-Missing values
Missing value replaced by mode for categorical data and for numeric data missing data replaced by mean
Correlation:
Some factors were multicollinear in which cases the dominant feature was take and non-dominant was dropped for example we create one new column the diff of visit date time and reserve date time drop the reserve date time
EDA Exploratory Data analysis:
Line plot, pie plot, Bar charts, heat maps, Box plot were plotted to know relationships between features

What u found from this EDA:
1.The feature correlation could be understood.
2.90% restaurant having less than 47 visitors on each day.
3. The number of unregistered visitors is far more than the number of registered visitors.
4. More number of restaurant having capacity less than 20
5.BOX plot: a. Minimum visitor is almost reaching to zero
	       b. Mean of visitor is 20
	       c. The maximum visitor between 55-60
	       d.25th Percentile and 75th percentile approximate value is 13 and 30 respectively
	       e. Average reservation is less than 10
	       f.25th and 75th percentile reservation is 20 and 40 respectively
6. Izakaya is the most popular genre in Japan as almost 23.8% of restaurants are of Izakaya genre. The second most popular genre in Japan is Cafe/Sweets having almost 21.8% restaurant market share.
7.On mid of 2016 there is sudden increase of number of restaurant from 300 – 700.
8. There is a sharp decrease at new year’s eve as most of the restaurants remain close on new year eve.
9. Even on daily basis, the restaurants observe highest number of visitors on Saturday. Second highest number of visitors is on Sunday. On Monday and Tuesday there is least number of visitors. Thursday and Wednesday has almost same visitor’s trends.
10. The maximum numbers of visitors is observed in the month of December.
11. more visitors observed on holidays than working days.
12. The highest number of visitors is between 5:30 PM to 7:00 PM (approx.).
13. There are no (almost zero) visitors between 12:00 AM and 7:00 AM (approx.), it may be because restaurants stay closed during night.  

Which Feature selection techniques u used:
1.Variance influence factor
2. calculating feature importance we used DecisionTreeRegressor.
               3. By using Recursive Feature Elimination we we got 61 essential features.
Have u performed any feature engineering? Means have u created new features?
1.Yes overall we have engineered 85 feature, from time series data first converted into date time and this date time data used to form a day, hour, week of day, year, Week, Quarter column.
2.Label Encoder is used to convert the categorical data to numeric data.

How u selected ML algorithms?
This is a regression problem KNeighborsRegressor, SGDRegressor, DecisionTreeRegressor, RandomForestRegressor , XGBRegressor,

Which performs metrics u used?
RMSLE:
From ML perspective, this is a straightforward regression problem, meaning we can use any one of the MSE, RMSE and MAE. However, for this problem, we will use RMSLE, which stands for Root Mean Square Logarithmic Error. This is the same as RMSE, except on the log form of a prediction.
•	The best RMSLE we got is 0.51436 from XGBRegressor (GBDT) and hence XGBRegressor (GBDT) is the best model.

Challenges u faced?
In this project we’re challenged to use reservation and visitation time series data to predict the total number of visitors to a restaurant for future dates. Among the challenges, we will discuss trends and seasonality of the data, external influencing factors such as holidays and special events.Such a system requires that all of the stages in the process, including tuning, features and model selection, will be done automatically.

How client get benefitted using this project in terms of some numbers %, or values :
The model testing was deployed and client test  the model  and the model after that client response is model give the 56% correct predict of how many visitor visit the restaurant it will not give the correct value but it will give the idea of how many visitor visit the restaurant. 


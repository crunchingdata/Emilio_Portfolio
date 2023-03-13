# Emilio_Portfolio
data science portfolio
# Project 1 overview: Estimator of weekly return on share price
* Created a tool that estimates the return per calendar week of a share to help investors get a broad timing for orders over the year. 
* Implemented a search engine that accesses the identification of most shares on the market from API https://www.alphavantage.co/
* Working per share on about in example ING Bank~[5877 rows x 9 columns] covering 20+ years of historical data from same API.
* Preprocessed data from daily open and close prices to daily return with Python and library Pandas.
* Model 1 for the weekly return estimation through flexible timeperiod selection and equaly weighted year relevanz for the return.
* Model 2 for the weekly return estimation through felxible retrospective timeperiod selction and exponential weighted year relevanz for the return.
* Model 3 for conrol of Model 2 through same timeperiod as Model 2 and weighted year relevanz implemented with the Formula for Exponential Moving Average (EMA).
* Crossmodel of Model 1 and Model 2 for more security of the forecast.

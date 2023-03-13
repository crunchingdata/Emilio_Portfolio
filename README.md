# Emilio_Portfolio
data science portfolio
# Project 1 overview: Estimator of weekly return on share price
* Created a tool that estimates the return per calendar week of a share to help private investors get a broad timing for orders over the year. 
* Implemented a search engine that accesses the identification of most shares on the market from API https://www.alphavantage.co/
* Working per share on about in example ING Bank~[5877 rows x 9 columns] covering 20+ years of historical data from same API.
* Preprocessed data from daily open and close prices to daily return with Python and library Pandas.
* Model 1 for the weekly return estimation through a flexible time period selection and equally weighted year relevant for the return.
* Model 2 for the weekly return estimation through a flexible retrospective time period selection and exponential weighted year relevant for the return.
* Model 3 for control of model 2 through the same time period as Model 2 and weighted year relevant implemented with the Formula for Exponential Moving Average (EMA) for the return.
* Cross-model of Model 1 and Model 2 for more security of the forecast.

Example: Estimated return of ING Bank:

![](/Images/INGreturnanalysis20082010.jpg)
![](/Images/INGretrospectivereturnanalysis12years.jpg)
![](/Images/INGreturncrossanalysis2008201012years.jpg)

# Emilio_Portfolio
data science portfolio
# Project 1 overview: Estimator of weekly return on share price
* Created a tool that estimates the return per calendar week of a share to help private investors get a broad timing for orders over the year. 
* Implemented a search engine to access identification of shares on the market from API 
* Preprocessed data from daily open and close prices to daily return.
* Builded Model 1 for weekly return estimation through a flexible time period selection and equally weighted return per year.
* Builded Model 2 for weekly return estimation through a retrospective time period selection and weighted return per yearly exponential decay.
* Builded Model 3 to control model 2 through the same time period and weighted return per yearly decay through implemented Exponential Moving Average (EMA) .
* Builded Cross-model of Model 1 and Model 2 for better forecast.

## Code and resources used
* Python 3.9.15.
* Packages: pandas, numpy, math, plotly.express, plotly.graph_objects, requests, json.
* dataset: per company on about exemplary ING Bank~[5877 rows x 9 columns] covering 20+ years of historical data from API https://www.alphavantage.co/.

## Example: Estimated return of ING Bank share price

![](/Images/INGreturnanalysis20082010.jpg)
![](/Images/INGretrospectivereturnanalysis12years.jpg)
![](/Images/INGreturncrossanalysis2008201012years.jpg)

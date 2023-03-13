# Emilio_Portfolio
data science portfolio
# Project 1 overview: Estimator of weekly return on share price
* Created a tool that estimates the return per calendar week of a share to help private investors get a broad timing for orders over the year.
* Implemented an exponential decay to optimize Exponential Moving Average (EMA).
* Builded various models to reach best forecast for (equal) weighted weekly return.

## Code and resources used
* Python 3.9.15.
* Packages: pandas, numpy, math, plotly.express, plotly.graph_objects, requests, json.
* dataset: dynamic data per company on about exemplary ING Bank~[5877 rows x 9 columns] covering 20+ years of historical data from API https://www.alphavantage.co/.

## Data cleaning
* Implemented a search engine to access identification of shares on the market from API 
* cleared datafrom irrelevant metrics and time periods.
* Preprocessed data from daily open and close prices to daily return.
* Preprocessed daily return (equal) weighted weekly return.

## EDA exemplary on estimated return of ING Bank share price
* Builded Model 1 for weekly return estimation through a flexible time period selection and equally weighted return per year.

![](/Images/INGreturnanalysis20082010.jpg)

* Builded Model 2 for weekly return estimation through a retrospective time period selection and weighted return per yearly exponential decay.
* Builded Model 3 to control model 2 through the same time period and weighted return per yearly decay through implemented Exponential Moving Average (EMA).

![](/Images/INGretrospectivereturnanalysis12years.jpg)

* Builded Cross-model of Model 1 and Model 2 to reach best model for forecast.

![](/Images/INGreturncrossanalysis2008201012years.jpg)

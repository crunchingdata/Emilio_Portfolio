# Emilio_Portfolio
data science portfolio
# Project 1 overview: Estimator of weekly return on share price
* Created a tool that estimates the return per calendar week of a share to help private investors get a broad timing for orders over the year.
* Implemented an exponential decay to optimize Exponential Moving Average (EMA).
* Built various models to reach best forecast for (equal) weighted average weekly return.

## Code and resources used
* Python 3.9.15.
* Packages: pandas, numpy, math, plotly.express, plotly.graph_objects, requests, json.
* dataset: dynamic data per company on about exemplary ING Bank~[5877 rows x 9 columns] covering 20+ years of historical data from API https://www.alphavantage.co/.

## Data cleaning
* Implemented a search engine to access identification of shares on the market from API 
* cleared data from irrelevant metrics and time periods.
* Preprocessed data from daily open and close prices to daily return.
* Preprocessed daily return (equal) weighted weekly return.

## EDA exemplary on estimated return of ING Bank share price
* Built Model 1 for weekly return estimation through a flexible time period selection and equally weighted return per year.

![](/Images/INGreturnanalysis20082010.jpg)

* Built Model 2 for weekly return estimation through a retrospective time period selection and weighted return per yearly exponential decay.
* Built Model 3 to control model 2 through the same time period and weighted return per yearly decay through implemented Exponential Moving Average (EMA).

![](/Images/INGretrospectivereturnanalysis12years.jpg)

* Built Cross-model of Model 1 and Model 2 to reach best model for forecast.

![](/Images/INGreturncrossanalysis2008201012years.jpg)

## Model Building
First I interpreted the goal of predicting return development of a share price. So, first I buildt Model 1 because a relevant argument is, that there could be liekly a repetition of events of the current ones in the past and with them a similar development of values in the stock market. Second, I applied with Model 2 a common forecasting technik of projecting past developement, thus taking past from current year back through exponential decay. For this it was necesary to control the outcome with an often used metric by private investors, the Expnential Moving average (EMA) at Model 3. 
At this point there where three main problems to solve: price differenz over time, uncertainty of the exact week and the irregular calendar week 53.
* Solution: usage of percentage, taking in account a moving three week average and making a case distinction.
* Model 1: Here is to select a time period with similar events. Exemplary the period post the finance crisis 2008 and current post Covid-19 and ucrainian war.
* Model 2: Time period will end with weight 10% consideration of the oldest year. The decay factor is been calculated through the total of years of the period. Young years are considered heavy in account.
* Model 3: 

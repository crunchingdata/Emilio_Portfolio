# Emilio_Portfolio
data science portfolio
# Project 1 overview: Estimator of weekly return on share price
* Created a tool that estimates the return per calendar week of a share to help private investors get a broad timing for orders over the year.
* Implemented an exponential decay to optimize Exponential Moving Average (EMA).
* Built various models to reach best forecast through (equal) weighted average for weekly return.

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
I started model building with interpreting the goal of predicting return development of a share price. So, first I buildt Model 1 since a relevant argument usually is, that there likely could be a repetition of past events in the current ones and with thies events a similar development in the share price. In Model 1 is to set a timeperiod with bounding years. Exemplary 2008-2010: Thies will show yearly overlapping and equal weighted weekly return through the post the finance crisis 2008, if it is wished to compare it with the current developement post Covid-19 and ucrainian war. 
Secondly, with Model 2 I applied a common forecast technic of projecting past developement, thus weighting yearly return from current return back through exponential decay. Model 2 was necesary to control in Model 3 with an often used metric here the Exponential Moving Average (EMA) to confirm return estimation.
* At this point there where three main problems to solve: price difference over time, uncertainty of return dexelopement at an exact week and the irregular calendar week 53. 
* Solution respectively: usage of percentage, taking in account a moving three week average and making a case distinction.
## Instructions of use
* Model 1: Here is to select a time period with similar events. 
* Model 2: Time period will end with weight 10% consideration of the oldest year. The decay factor is been calculated through the total of years of the period. Young years are considered heavy in account.
* Model 3: 

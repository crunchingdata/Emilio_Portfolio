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
I started the model building by interpreting the goal of predicting return development of a share price. <br>
So, first I buildt Model 1 since a relevant argument usually is, that there likely could be a repetition of past events in the current ones and with this events a similar development in the share price. In Model 1 is to set a timeperiod with bounding years. Exemplary 2008-2010: This will show yearly overlapping and equal weighted weekly return through the post the finance crisis 2008, if it is wished to compare it with the current developement post Covid-19 and ucrainian war.<br>
Secondly, with Model 2 I applied a common forecast technic for trend continuing past developement, thus weighting yearly return from current return back to the return of past years with exponential decay. Model 3 was necesary to control Model 2 with an often used metric here the Exponential Moving Average (EMA) over years to confirm return estimation.

* At this point there where three main problems to solve: price difference over time, inaccuracy of the exact week for a certain return, the irregular calendar week 53 and setting a visual for return over +/- developements of more that one week.
* Solution respectively: usage of percentage, taking in account a moving three week average, making a case distinction and bounding a accumulated return to the sign of the three week average.

At least, I buildt a cross-model, that combines Model 1 with Model 2 in order to combine estimation based on both arguments for return estimation, compare the current period with a past period and continuing a current trend. Due to more scattering by more years in a period the extrem values in a model decrease, so that the estimation of the return in the cross model works best, if the periods of Model 1 and Model 2 to are of similar length. +/- return periods remain untouched by this.
## Instructions of use
* Model 1: Here is to select a time period with similar events as the current ones. 
* Model 2: 
Time period will start with weight 10% on return of the oldest year. The decay factor is been calculated through the total of years of the period. Young years are considered heavy in account.

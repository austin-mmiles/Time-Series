# Time-Series
## Abstract
The market for cars go through various increase and decreases in sales over time. The data set we use
provides us monthly sales for cars in Quebec, Canada from 1960 to 1967. Using this data set, our goal is to
forecast the amount of cars sold within the next 12 months and compare that to the actual number of cars
sold in each of those 12 months. Forecasting these amounts will provide insight to fluctations in car sales
which can benefit those who want to sell a car at an optimal time or buy a car at an optimal time.
We are able to compare the actual results because we create a training set which does not include the last
12 months and perform our analysis on that set. For forecasting to be effective, the data must be stationary
so we used a log transformation as well as differencing to get rid of the trend and seasonal component.
After observing the ACF and PACF of the newly transformed data we get 3 potential SARIMA models
which we compared AIC, examined residuals, performed diagonstics, calculated casuality and invertibility.
We concluded that the model SARIMA (2,0,0) x (0, 1, 1)12 was the most suitable model from these tests.
The 95% confidence interval of the forcasted values were accuarately able to contain the true results for the
months in 1968.
## Introduction
We want to forecast the future trends in car sales in Quebec to provide insights on when it is a good time
to buy or sell a car. Basic economics teach us that when there are a lot of cars being sold, the car price is
high; but when there is not a lot of cars being sold, the price is low. The data set contains 9 years worht
of monthly car sales but we will only use the first 8 years in our study so that we can use the 9th year to
compare our results and find our models accuracy. We load our Quebec car sales data into R and remove
the last 12 observations as our test set for the forecasts. We then go into exploratory analysis and found
that the data requires transformations to stabilize variance and differencing to remove trend and seasonality.
Then we examine the ACF and PACF of the stationary series to identify appropriate models. We get three
potential models which we conduct model diagnostics to make it a valid SARIMA. In the end, we use the
model with the lowest AICc to forecast the next 12 observations which we compare to the test set, to evaluate
the model’s accuracy. The model we ended with was a good fit for our data, however we were unable to
normalize the dataset perfectly which is common with real world datasets. We retrieved the data from
https://data.world/perceptron/monthly-car-sales-quebec-1960 and used R for our analysis.

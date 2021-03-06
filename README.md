# Beijing Air Pollution Time Series Analysis

![alt text](https://post.medicalnewstoday.com/wp-content/uploads/sites/3/2020/04/iStock-1180072881-1200x628.jpg.png)

## Business Problem

Air pollution has been an increasingly prevelant problem all over the world, but particularly China. Energy related emmision increased over 80% in the past 10 years leading to the accleration of global warming as well as increased number of deaths. In 2015 it was estimated that nearly 1.6 million deaths in China were attributed to the high pollution levels in the country. To mitigate such harm, it is important to understand our relationship with the climate through historical data. To truly put our best foot forward, would be to use data insights into predicting future air pollution and how we can better understand from historical data the right and wrong paths taken. 

## The Data
The dataset used is the [Beijing Air Pollution](https://archive.ics.uci.edu/ml/datasets/Beijing+Multi-Site+Air-Quality+Data). The dataset contains just over 1200 rows and 9 columns that we manipulated when we were importing the data. Please see the Getting the Data notebook to get the full picture. I also decided to resampe the datset with daily frequency for both easier handling and proximity to real use case scenarios.

## EDA
![Alt text](Time-series-Analysis-Air-Pollution/results/Trends.png) 

The EDA focused around time series decomposition. We break the time series into 4 components: level, trend, Seasonality, and noise. We have to make sure that our data is stationary by performing multiple tests as well as splitting our series into smaller ones to identify subtrends. We also perform a Dickey-Fuller Test to confirm stationarity.

![Alt text](Time-series-Analysis-Air-Pollution/results/pollution.png) 

## Models Tested
- Autoregressiion(AR)
- Autoregressive moving Average (ARIMA)
- Seasonal Autoregressive integrated moving average (SARIMA)
- XGBoost
- Prophet
- DeepAR
- Lightgbm

## Results

Below is a graphic representation of the Autoregressive model. We can see the Autoregressive model performs alright on the dataset and predicts well enough to capture the major swings in the time series datset.
![Alt text](Time-series-Analysis-Air-Pollution/results/Autoregression.png) 

If we move over to ARIMA we see that the mode performs a lot better.It is almost identitical to the original dataset.

![Alt text](Time-series-Analysis-Air-Pollution/results/ARIMA.png) 

The best model was lightgbm with an RMSE of 43. The worst was DeepAR, partly I think becuase the datset is not large or robust enough.

## Future Steps

I will fix the Github to show all the RMSE and all the scores from each model. Another work on this project could be to apply Nueral Nets or other davanced models to see how well they perform.

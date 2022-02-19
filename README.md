# Predicting Heart Rate using Time Series Forecasting with Python

### The Ultimate Guide for Time Series Analysis and Forecasting on Heart rate Data

![image](https://user-images.githubusercontent.com/31254745/154763767-f42b7974-1105-4584-9a32-ea4b1a0fcbf5.png)

## Introduction
Sudden variations in heart rate could lead to the risks of stroke, heart failure, cardiac arrest, and also death. Preventing heart disease is important and with advancements in AI, predicting heart disease can have more accurate future predictions allowing healthcare sectors to detect and treat such situations at early stages making sure that more people can live healthy lives.

In this project, I will demonstrate and show how we can harness the power of Machine Learning and apply it in healthcare. I will walk you through the entire process of how to predict Heart rate using Time Series Forecasting with Python.

## What is Time Series Forecasting?
A time series is a sequence where a metric is recorded over regular time intervals. Depending on the frequency of observations, a time series may typically be hourly, daily, weekly, monthly, quarterly and annual.

Forecasting involves taking models to fit historical data and making predictions about the future of time-series data.

## But why forecast?

Because forecasting a time series is often of tremendous commercial value. In the healthcare domain, it drives the fundamental business planning, procurement, disease predictions and production activities. So, it’s important to get the forecasts accurate to save on costs and is critical to success.

## Problem Statement
The objective of this task is we are given a data set of time series collected using medical sensors, approximately four hours of data for a patient. Using these data, we will build an effective time series model to predict the next 20 observations (minutes) of heart rate data (Lifetouch Heart Rate).

![image](https://user-images.githubusercontent.com/31254745/154764015-65da6d52-e93a-455f-81e5-5fda814c5016.png)


## Overview of the Dataset	

Before attempting to solve the problem, it's very important to have a good understanding of the data.

- Get the descriptive statistics of the data
- Get the information about missing values in the data

## Exploratory Data Analysis

Exploratory data analysis is an approach to analyse or investigate data sets to find out patterns in the data. Primarily EDA is for seeing what the data can tell us beyond the formal modelling or hypothesis testing tasks.

### Handling Missing Values

Time Series algorithms don't work if the data is missing. So, we need to handle the missing values to get the predictions. There are various ways to handle missing values for time series data. 

- Forward Fill
- Backward Fill
- Replace

### Visualizing the Time series data

A line plot and area chart of a time series can provide a lot of insight into the problem. Some observations from the plot can include:
- Whether the trend appears to be level around the mean
- Whether there appear to be any obvious outliers

### Checking Distribution of the Time series data
We should check the distribution of the time series so that we can decide if we need to transform the data or can be used as it is. Additionally, it provides insights into the type of distribution the data follows.
- Histogram to check the distribution of the attribute
- Q-Q Plot to check Normal Distribution of attribute

### Time Series Decomposition

Depending on the nature of the trend and seasonality, a time series can be modelled as an additive or multiplicative, wherein, each observation in the series can be expressed as either a sum or a product of the components.
- Additive time series: Value = Base Level + Trend + Seasonality + Error
- Multiplicative Time Series: Value = Base Level x Trend x Seasonality x Error

### Stationarity test - Augmented Dickey-Fuller test (ADH Test)
There are multiple tests to test if a time series is stationary or not. The most commonly used is the ADF test, where the null hypothesis is the time series possesses a unit root and is non-stationary. So, if the P-Value in the ADH test is less than the significance level (0.05), we reject the null hypothesis.

### ACF-PACF plots and Order of Differencing
The right order of differencing is the minimum difference required to get a near-stationary series that roams around a defined mean and the ACF plot reaches zero fairly quick.

If the autocorrelations are positive for many numbers of lags (10 or more), then the series needs further differencing. On the other hand, if the lag 1 autocorrelation itself is too negative, then the series is probably over-differenced.

## Model Building – Time Series Forecasting

- Train – Test Split
- Model 1 ARIMA
- Model 2 Auto ARIMA
- Model 3 Simple Exponential Smoothing
- Model 4 Holt-Winters
- Model 5 FB Prophet

## Summary of Time Series Model Evaluation

Below is the summary table showing model evaluation metrics such as Root Mean Square Error (RMSE) score, Mean Absolute Error (MAE) Score on Training Data set for different time series models.

From all the models, the ARIMA model achieved the best MAE score around 3.316 implies the model is about 96.684% accurate in predicting the next 20 observations. Also, the lower value of the RMSE score of 4.203 indicates a better fit.

![image](https://user-images.githubusercontent.com/31254745/154765062-fdea88bf-ca40-428e-8f6e-d1fdbf0688fa.png)


## Interpreting the Residual plots in the ARIMA model
- Standardized Residual: The residual errors seem to fluctuate around a mean of zero and have a uniform variance.
- Density Plot: The density plot suggests normal distribution with a mean zero.
- Q-Q Plot: All the dots should fall perfectly in line with the red line. Any significant deviations would imply the distribution is skewed.
- Correlogram: ACF plot shows the residual errors are not autocorrelated. Any autocorrelation would imply that there is some pattern in the residual errors which are not explained in the model.

Overall better model and let's predict on test data and forecast.

## Predictions on Test Data

![image](https://user-images.githubusercontent.com/31254745/154765244-bb0f7a63-bd97-4fd4-b943-4a443f15b052.png)

## Forecast on Next 20 Heart Rate Observations

![image](https://user-images.githubusercontent.com/31254745/154765292-2af0302a-2fea-4bc8-84f8-c377d75a239b.png)

## Conclusion
In this project, we have learnt how to approach a Time Series forecasting problem. We started with an understanding problem, exploration of data. Then we handled missing values, stationary tests and visualised time series data.

Finally, we were able to apply different Time series algorithms and make forecasts (future predictions) on the data set using the best Time series model ARIMA which outperformed the other models.














# Practice Lab M05 (Version 3)
## Time Series Forecasting, Anomaly and Rule mining

Practice Lab M04 will focus on how to do the time series forecasting, anomaly detection and rule mining

## To do

- Use ARIMA to predict the time series
- Using isolation forest to find the anomaly
- Conduct the association rule mining.


## Tasks 1 Time series and Anomaly detection
### Task 1.1 Reading time series
We first read the given time series. However, before doing any forecasting, we will need to define some error metrics for evaluation purpose. In there we will use mean abusolute percentage error and mean abusolute error

- read the time series by using pandas and plot the time series
- defne the function of mean abusolute percentage error in numpy

### Task 1.2 Moving average smoothing forecasting
After having the time series, let's do Moving Average Smoothing Forecasting

- define the moving average function by numpy
- use pandas to conduct the moving average with window size of 3
- plot the upper bound and lower bound by using the mean abusolute error + 1*standard deviation
- plot the original time series, the moving avergae time series and the upper bound and lower bound together


### Task 1.3 Anomaly detection
After having the original time series, the moving avergae and the upper bound and lower bound in one plot, we could see some anomalies, could we use isolation to detect them

- write code for training the isolation on original time series
- find the anomalies in original time series and mark them in the plot with original time series


### Task 1.4 Exponential smoothing forecasting
Now we would like to try the exponential smoothing forecasting.

- Using given exponential smoothing forecasting function to obtain the new time series
- plot the exponential smoothing forecasting time series with original together in one plot


## Task 2 ARIMA
### Task 2.1 Find parameter p, d and q
Now we want to find the parameter of p, d and q for ARIMA before training

- Use adfuller test to determine the d
- Use pacf and acf plot to draw the auto correlation plot for p and q


### Task 2.2 Train the ARIMA
Now we will use the parameter p, d and q to train the ARIMA

- train the ARIMA and plot the fitted time series with original time series together

### Task 2.3 (Advanced) Assocaition Rule Mining
We want to do the association rule mining, but before doing it, we will need to discrete the value from given time series

- Run the discretization by using provided code
- Run the rule mining and print the rule

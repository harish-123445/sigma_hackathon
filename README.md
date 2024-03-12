# Sigma Hackathon Project using APPLE stock data

#### DESCRIPTION
This QuantRocket project retrieves and analyzes daily Apple (AAPL) stock data for the year 2023, specifically focusing on the date and closing price. The project utilizes QuantRocket's data fetching capabilities to obtain historical data and perform basic analysis.


#### ANALYSIS AND MODEL BUILDING
This project focuses on the analysis and forecasting of time series data using various techniques. The main features implemented in the project include:
- Data Extraction using Quantrocket
```python
import pandas as pd
from quantrocket.history import get_prices

# Define parameters for data extraction
sids = 'FIBBG000B9XRY4'
start_date = '2023-01-01'
end_date = '2023-12-31'
data_frequency = 'daily'
fields = 'Close'

# Get historical prices using QuantRocket Zipline
data = get_prices("usstock-free-1min",
                  data_frequency=data_frequency,
                  sids=sids,
                  start_date=start_date,
                  end_date=end_date,
                  fields=fields)

# Display the extracted data
print(data.head())
```

- Output of Model for Finding the Optimal Portfolio Value and Transition Probability
  ### Portfolio Analysis Results

```python
Final Portfolio Value: 17

Optimal Buy Indices: 
[6, 8, 12, 16, 21, 28, 30, 33, 36, 39, 41, 45, 50, 52, 57, 59, 61, 64, 66, 69, 79, 85, 88, 94, 97, 100,
 103, 108, 110, 113, 117, 120, 123, 128, 133, 136, 142, 145, 147, 154, 156, 160, 164, 169, 173, 177, 179,
 183, 187, 191, 196, 201, 204, 207, 209, 212, 216, 218, 232, 234, 236, 238, 243]

Transition Matrix:
         Bear  |   Flat    |     Bull
Bear  0.138889 |  0.722222 |  0.138889
Flat  0.146497 |  0.598726 |  0.254777
Bull  0.125000 |  0.678571 |  0.196429
```


#### VISUALIZATIONS
- Moving Average Plot

![Moving Average Plot](https://github.com/harish-123445/sigma_hackathon/blob/main/Output/moving_average.png)

- Time Series Decomposition
![Moving Average Plot](https://github.com/harish-123445/sigma_hackathon/blob/main/Output/decomposition.png)

- ARIMA Model Prediction
![Moving Average Plot](https://github.com/harish-123445/sigma_hackathon/blob/main/Output/arima.png)

- XGBoost Forecasting
![Moving Average Plot](https://github.com/harish-123445/sigma_hackathon/blob/main/Output/XGboost%20forecasting.png)

- Differenced Time series
![Moving Average Plot](https://github.com/harish-123445/sigma_hackathon/blob/main/Output/differenced.png)

- ADFuller Test
## Stationarity Test Results

The Augmented Dickey-Fuller (ADF) test was conducted to assess the stationarity of the time series. Here are the results:

| Statistic | Value |
|---|---|
| Test Statistic | -2.5861 |
| p-value | 0.0959 |

**Interpretation:**

With a test statistic of -2.5861 and a p-value of 0.0959, we **fail to reject the null hypothesis** of non-stationarity at the 5% significance level. This suggests that the time series is likely **non-stationary**.

**Note:**

A higher p-value (greater than 0.05) indicates that we fail to reject the null hypothesis, meaning we cannot conclude with strong evidence that the series is stationary. In this case, further steps might be required to make the series stationary before proceeding with certain types of analysis.

## Forecasting for next n days from jan1 2024 (say 14 days) using ARIMA
![](https://github.com/harish-123445/sigma_hackathon/blob/main/Output/arima_for_n_days.png)



## Overview

The analysis is conducted in a Jupyter Notebook (`sigma-forecasting_and_model.ipynb`) and covers a comprehensive exploration of time series data. The main steps and findings are summarized below.

### Moving Average Plot

A moving average plot is generated to smooth out fluctuations in the time series data, providing a clearer picture of the underlying trends.

### Time Series Decomposition

Time series decomposition is performed to separate the data into its trend, seasonality, and residual components. This helps in understanding the various contributing factors to the overall pattern.



### XGBoost Forecasting

XGBoost, a powerful machine learning algorithm, is employed for time series forecasting. The model is trained on historical data to predict future values.

### ADFuller Test

The Augmented Dickey-Fuller (ADF) test is conducted to assess the stationarity of the time series data. This is a crucial step in time series analysis and model building.

### Optimal Portfolio Value

A model is implemented to find the optimal portfolio value based on the given time series data. This involves optimizing investment allocations for maximum returns.

### Data Extraction with QuantRocket Zipline

QuantRocket Zipline is used for efficient data extraction, allowing seamless integration of financial data into the analysis.

## GOOGLE COLAB LINK
You can find the visualizations and other plots in this link
[Click here for Google colab file](https://colab.research.google.com/drive/1MmX-zYitCwlZABgCpxSLmU72MqVrq7sW?usp=sharing)  

### Forecasted Values for the Next 14 Days

These are the forecasted stock prices for the next 14 days based on the ARIMA model. The table below provides the day index and the corresponding forecasted values.

| Day | Forecasted Value |
|-----|-------------------|
| 250 | 192.425871        |
| 251 | 192.477162        |
| 252 | 192.451898        |
| 253 | 192.464342        |
| 254 | 192.458212        |
| 255 | 192.461232        |
| 256 | 192.459744        |
| 257 | 192.460477        |
| 258 | 192.460116        |
| 259 | 192.460294        |
| 260 | 192.460206        |
| 261 | 192.460249        |
| 262 | 192.460228        |
| 263 | 192.460239        |

### Conclusion

In this project, we utilized time series analysis techniques, specifically the ARIMA model, to forecast the stock prices of Apple for the next 14 days. The analysis involved loading historical stock price data for the year 2023, fitting an ARIMA model, and visualizing both the historical and forecasted stock prices.

#### Key Results:
- **Forecasted Values:** The table above provides the forecasted stock prices for the next 14 days, starting from day 250 onwards.

- **Interactive Plot:** The interactive plot showcases the historical stock prices and the forecasted values in an easy-to-understand visual format.
- **Optimized portfolio values** - the plots and transition probability matrices shows the optimized buy indices and portfolio values

This project serves as a starting point for time series forecasting and can be extended with more sophisticated models, feature engineering, and additional data sources. Feel free to explore and adapt the code to suit your specific needs.

Thank you for exploring this time series forecasting project!







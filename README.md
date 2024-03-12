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
- Time Series Decomposition
- ARIMA Model Prediction
- XGBoost Forecasting
- ADFuller Test


## Overview

The analysis is conducted in a Jupyter Notebook (`project.ipynb`) and covers a comprehensive exploration of time series data. The main steps and findings are summarized below.

### Moving Average Plot

A moving average plot is generated to smooth out fluctuations in the time series data, providing a clearer picture of the underlying trends.

### Time Series Decomposition

Time series decomposition is performed to separate the data into its trend, seasonality, and residual components. This helps in understanding the various contributing factors to the overall pattern.

### ARIMA Model Prediction

An ARIMA (AutoRegressive Integrated Moving Average) model is utilized for time series prediction. The model parameters are tuned to achieve the best possible forecasting accuracy.

### XGBoost Forecasting

XGBoost, a powerful machine learning algorithm, is employed for time series forecasting. The model is trained on historical data to predict future values.

### ADFuller Test

The Augmented Dickey-Fuller (ADF) test is conducted to assess the stationarity of the time series data. This is a crucial step in time series analysis and model building.

### Optimal Portfolio Value

A model is implemented to find the optimal portfolio value based on the given time series data. This involves optimizing investment allocations for maximum returns.

### Data Extraction with QuantRocket Zipline

QuantRocket Zipline is used for efficient data extraction, allowing seamless integration of financial data into the analysis.

## Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/timeseries-analysis-project.git

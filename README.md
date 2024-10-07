# Stock Market Prediction Using Machine Learning

## Table of Contents
1. [Stock Analysis: Fundamental Analysis vs. Technical Analysis](#stock-analysis-fundamental-analysis-vs-technical-analysis)
2. [Stock Prices as Time-Series Data](#stock-prices-as-time-series-data)
3. [Dataset Analysis](#dataset-analysis)
4. [Creating a Neptune.ai Project](#creating-a-neptuneai-project)
5. [Evaluation Metrics and Helper Functions](#evaluation-metrics-and-helper-functions)
6. [Predicting Stock Price with Moving Average (MA) Technique](#predicting-stock-price-with-moving-average-ma-technique)
7. [Introduction to LSTMs for Time-Series Data](#introduction-to-lstms-for-time-series-data)
8. [Final Thoughts on New Methodologies](#final-thoughts-on-new-methodologies)

## Stock Analysis: Fundamental Analysis vs. Technical Analysis

When it comes to stocks, fundamental and technical analyses are at opposite ends of the market analysis spectrum.

**Fundamental Analysis** evaluates a company’s stock by examining its intrinsic value, including tangible assets, financial statements, management effectiveness, and more. 

**Technical Analysis** analyzes measurable data from stock market activities such as stock prices and volume. In this project, we focus on technical analysis, specifically the Moving Average (MA) technique and LSTM.

## Stock Prices as Time-Series Data

Stock prices can be treated as time-series data, as they are observations taken at successive points in time. Time series forecasting can apply techniques like Moving Averages to smooth out short-term fluctuations and predict future trends.

## Dataset Analysis

We use the closing prices of Apple’s stock (AAPL) from the past 21 years (1999-11-01 to 2021-07-09), retrieved from Alpha Vantage. For model training, 80% of the dataset is used, while 20% is reserved for testing.

### Data Retrieval

Data was collected using the Alpha Vantage API. You can find the API tutorial [here](https://www.alphavantage.co/support/#api-key). Alternatively, the dataset used is available [here](https://example.com).

## Creating a Neptune.ai Project

Neptune.ai was integrated into this project for tracking experiments and logging metrics during model training. You can find the Neptune project setup in `notebooks/neptune_setup.ipynb`.

## Evaluation Metrics and Helper Functions

The model performance is evaluated using the following metrics:
- **RMSE**: Root Mean Squared Error, measuring the difference between predicted and actual stock prices.
- **MAPE**: Mean Absolute Percentage Error, representing the percentage difference between predicted and actual prices.

Helper functions for metrics calculation and data handling are located in `src/metrics.py`.

## Predicting Stock Price with Moving Average (MA) Technique

We use both **Simple Moving Average (SMA)** and **Exponential Moving Average (EMA)** techniques to predict stock prices. The implementation is detailed in the notebook `notebooks/ma_prediction.ipynb`.

## Introduction to LSTMs for Time-Series Data

LSTM (Long Short-Term Memory) is a powerful algorithm designed for time-series data, which excels at capturing historical patterns and predicting future values. 

The key component of an LSTM is the **Cell State (Ct)**, representing the internal memory. The model contains three gates:
- **Forget Gate**: Decides which information to discard from the current cell state.
- **Input Gate**: Selects which new information to add.
- **Output Gate**: Controls the output passed to the next cell state.

We implement LSTM to predict stock prices and compare it against SMA and EMA models. Detailed implementation can be found in the notebook `notebooks/lstm_prediction.ipynb`.

## Final Thoughts on New Methodologies

While LSTM and Moving Averages are powerful, new models such as **Prophet** or **ARIMA** could also offer improved forecasting for stock prices. Further research in combining these methodologies could enhance accuracy.


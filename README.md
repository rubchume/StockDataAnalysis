# Introduction

This project explores stock data forecasting and trading strategies that make use of that forecast.

The intent is not to create some production ready trading strategy, but to showcase some popular time series statistical models (ARIMA, SARIMAX, Simple Exponential Smoothing), how to train them, and how to use the forecasts in real strategies using the Backtrader Python library. I have also made use of technical analysis tools like Bollinger Bands.

# Data description

The data is stored in this excel file: [2020Q1Q2Q3Q4-2021Q1.xlsx](2020Q1Q2Q3Q4-2021Q1.xlsx).

It presents day stock values for multiple stocks from all over the world (one stock per Excel sheet) from 2020 and 2021.
The companies are:
- Sberbank Rossii PAO (Russia)
- Koc Holding AS (Turkey)
- Medinet Nasr Housing (Egypt)
- Minerva SABrazil (Brazil)
- Pampa Energia SA (Argentina)
- Cementos Argos SA (Colombia)
- Impala Platinum (South Africa)
- Dongkuk Steel Mil (South Korea)

# Approach

Each stock has been modeled using classical statistical models for time series: ARIMA, SARIMAX, Simple Exponential Smoothing.

Then, a simple strategy using Bollinger Bands has been implemented in Backtrader and backtested.

# Conclusions

From the classical analysis, we can see that there is not so much useful information in stock prices besides the fact that the best predictor of tomorrow's price is today's price for any stock. Of course there were some subtleties, but the general lesson we can take is that every useful statistical information is already being used to make profit by someone in the stock market, so there remaining patterns to be analyzed are too subtle to be modeled by such naive models as SARIMAX.

Those models are very useful for other type of time series data, like natural phenomena, but they are not enough for data where everyone is trying to make a profit, changing the statistical properties in every buy and sell operation.

The Bollinger Band strategy was simple but good, but thanks to the backtesting we saw that 2020 (COVID) was actually a bad year for almost everyone in the markets. However, it would be interesting to extend the backtesting to posterior years.

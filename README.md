# Project-2 - Stock Price Prediction & Trading Predictions

We are using machine learning models to predict the stock (traded securities, including FX, commodities) prices as well as trading signals from certain traditional strategy to compare the models’ final returning results and select the best models for certain stocks (traded securities).
Hypothesis
we assume the trade can be always executed by the closing price without price spread effects with 0 trading commission cost to simplify the results.
For the pricing prediction, we assume that the stock prices can be predicted by machine learning models with its own historical price trend, as well as the external economic conditions data.
The prophet model can be used to capture the seasonality trend of stock prices volatile activities across time.
Each stock (traded securities) has its own best fit prediction models for pricing and trading strategy in certain period.

## Model Summary
* Prophet model analysis to check the seasonality of the stocks volatile activities
* Price prediction from Neuron Network and LSTM
* Price prediction from linear and regression models
* SVC and Decision Tree models for trading signals predictions with simple and double SMA crossover strategies
* Combining prediction and trading models to exam the results.


## Strategies for Feature Engineering

* Strategy_1: SMA21 & SMA50

When the shorter-term MA crosses above the longer-term MA, it's a buy signal, as it indicates that the trend is shifting up. This is known as a golden cross. Meanwhile, when the shorter-term MA crosses below the longer-term MA, it's a sell signal, as it indicates that the trend is shifting down. This is known as a dead/death cross.

* Strategy_2: EMA21 & EMA50

When the shorter-term MA crosses above the longer-term MA, it's a buy signal, as it indicates that the trend is shifting up. This is known as a golden cross. Meanwhile, when the shorter-term MA crosses below the longer-term MA, it's a sell signal, as it indicates that the trend is shifting down. This is known as a dead/death cross.

* Strategy_3: VWAP

long(Buy) when the price is below the VWAP and short(Sell) when the price is above VWAP.

* Strategy_4: RSI

When the RSI indicator crosses 30 on the RSI chart, it is a bullish sign and when it crosses 70, it is a bearish sign. Put another way, one can interpret that RSI values of 70 or above indicate that a security is becoming overbought or overvalued. It may be primed for a trend reversal or corrective price pullback. An RSI reading of 30 or below indicates an oversold or undervalued condition.

* Strategy_5: MACD

The strategy is to buy – or close a short position – when the MACD signal crosses above the zero line, and sell – or close a long position – when the MACD crosses below the zero line.

* Strategy_6: BolingerBands %B

A %B value above 0.5 indicates the closing price is above the upper band, suggesting an overbought market. Conversely, a %B value below 0.5 indicates the closing price is below the lower band, implying an oversold market. A %B value of 0.5 means the closing price is at the middle band or the simple moving average, indicating a neutral market condition.

* Strategy_7: OBV

**OBV hits a new high while the price tests resistance:** bullish divergence, predicting the price will break resistance and surge higher, playing catch-up.
**The price hits a new high while OBV grinds at or below the last resistance level:** bearish divergence, predicting the rally will stall or reverse.
**OBV hits new low while price tests support:** bearish divergence, predicting the price will break support and surge lower, playing catch up.
**The price hits a new low while OBV grinds at or above the last support level:** bullish divergence, predicting the sell-off will stall or reverse.
**OBV matches the price action, higher or lower:** bullish or bearish convergence, depending on direction.

* Strategy_8: ADX

ADX clearly indicates when the trend is gaining or losing momentum. A series of higher ADX peaks means trend momentum is increasing. A series of lower ADX peaks means trend momentum is decreasing.

## Neural Network and LSTM Price Predictor

Few points:
* Standard scaler works much better than MinMax scaler
* Standardize target for LSTM, for NN not necessary
* Re-scaling to improve loss didn’t work
* Even after plateau, further learning seemed to help

## Linear & Regressor Models

The output in terms of RMSE & MAPE for the best models selected varied with stocks chosen, we believe within a certain range of 2.5% MAPE we can predict the next 14 Day stock prices barring extreme tail events.

## SVC and Decision Tree Trading Signal Predictors

* SMA double window crossover strategy performance is not always good for different stocks. Sometimes, simple strategy’s performance is better with certain prediction models for some stocks.
* Decision Tree prediction model for effective trading signal predictions performs a bit better in some cases, the model prediction’s performance shows a stock price sliding prevention capability
* However, SVC seems has better prediction capability in continuous growing trends.

## Prophet

Facebook Prophet is a valuable tool for time series forecasting, offering a combination of simplicity, flexibility, and accuracy. Its ability to automatically handle seasonality, uncertainty estimation, and incorporation of external factors makes it a popular choice for businesses and researchers across different domains. However, users should still exercise caution and domain-specific knowledge when interpreting the forecasts generated by Prophet, as with any forecasting tool.





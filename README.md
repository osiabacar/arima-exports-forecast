# ARIMA Forecasting of Central African Republic Exports

Time series analysis and forecasting of Central African Republic exports from 1960 to 2017 in R, completed as my final project for STA 137 (Applied Time Series Analysis) at UC Davis.

## Objective
Build and evaluate ARIMA models to understand the structure of the exports series and produce a 5-year forecast with uncertainty intervals.

## Data
Course-provided dataset with annual country-level indicators (GDP, exports, population) for the Central African Republic, 1960–2017. This analysis focuses on **exports**.

## Methods
1. **Exploration:** plotted the raw series and its ACF/PACF; the slow, gradual ACF decay indicated a non-stationary series.
2. **Variance stabilization:** applied a Box-Cox transformation (estimated λ ≈ -0.365) to stabilize variance.
3. **Differencing:** took a first difference of the transformed series. The ACF dropped to near zero after lag 1, indicating stationarity.
4. **Model selection:** fit and compared three candidate models:
   - ARIMA(0,1,0): random walk
   - ARIMA(0,1,1): MA(1)
   - ARIMA(1,1,0): AR(1)
5. **Diagnostics:** evaluated each model using standardized residual plots, residual ACFs and Ljung-Box test p-values across lags 1–20.
6. **Forecasting:** produced a 5-year forecast from the ARIMA(1,1,0) model with 80% and 95% confidence intervals.

## Tools
R (forecast, tseries, ggplot2, dplyr), R Markdown

## Files
- `exports_arima_forecast.Rmd`: full analysis code
- `exports_arima_forecast.md`: rendered report with all plots

## Author
Oscar Abarca · [LinkedIn](https://www.linkedin.com/in/oscar-abarca-09a384279)

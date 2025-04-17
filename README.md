# Microsoft Stock Price Analysis & Linear Regression Forecasting

This project explores historical stock data of **Microsoft (MSFT)** using Python for preprocessing, visualization, and predictive modeling. A simple **Linear Regression** model is trained to forecast stock closing prices based on time indices.

---

## Dataset Overview

- **Source:** [NASDAQ / Yahoo Finance](https://www.nasdaq.com/market-activity/stocks/msft/historical) *(Data not included here due to licensing restrictions)*
- **Records:** 1511 daily entries
- **Date Range:** Likely spans from ~2015 to March 31, 2021
- **Features:**
  - `Date`: Timestamp of trading day
  - `Open`, `High`, `Low`, `Close`: Prices in USD
  - `Volume`: Number of shares traded

---

## Data Preprocessing

- Loaded data using `pandas`
- Verified that no missing values exist
- Converted `Date` column to `datetime` format
- Outlier inspection via box plots

---

## Exploratory Data Analysis (EDA)

Visualization with `matplotlib` and `seaborn`:
- **Line plots** for `Open`, `High`, `Low`, `Close`, and `Volume`
- **Observations:**
  - Prices show a general **upward trend** over time
  - **Volume** exhibits **seasonality**

---

## Model: Linear Regression

- Target Variable: `Close` price
- Feature: Index-based time step (not ideal for real forecasting but used for demonstration)
- Split: 80% train / 20% test
- **Scaler:** `StandardScaler` applied to input feature
- **Model:** `LinearRegression` from `sklearn`

---

## Predictions & Plotting

- Used `plotly` for interactive visualizations
- Compared **actual vs. predicted** `Close` prices on training data

---

##  Evaluation Metrics

| Metric    | Training Set | Test Set    |
|-----------|--------------|-------------|
| R² Score  | 0.9036       | 0.8871      |
| MSE       | 316.87       | 329.56      |

The model fits the data reasonably well despite using a simplistic time index as input.

---

## Key Takeaways

- Linear Regression captures **trend** but lacks **seasonal/volatility sensitivity**
- Future improvement could involve:
  - Time-series models like **ARIMA**, **Prophet**, or **LSTM**
  - Including **technical indicators** (e.g., moving averages)

---

## Tools & Libraries

- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `sklearn`: preprocessing, model, evaluation
- `plotly`: interactive visualization

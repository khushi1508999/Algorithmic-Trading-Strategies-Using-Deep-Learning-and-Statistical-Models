# Algorithmic-Trading-Strategies-Using-Deep-Learning-and-Statistical-Models

A data-driven stock analysis project that leverages **ARIMA**, **Prophet**, **LSTM**, and **GARCH** models to forecast stock prices and optimize portfolio allocation for short-term trading on the **StockGro** platform.

---

## 🧾 Table of Contents

1. [📌 Project Overview](#-project-overview)
2. [🎯 Objectives](#-objectives)
3. [📚 Methodology & Models](#-methodology--models)
4. [📊 Stock Selection Rationale](#-stock-selection-rationale)
5. [🔍 Data Sources & Preprocessing](#-data-sources--preprocessing)
6. [📈 Forecasting Strategy](#-forecasting-strategy)
7. [💼 Portfolio Construction](#-portfolio-construction)
8. [📉 Model Performance & Metrics](#-model-performance--metrics)
9. [📱 StockGro Simulation Results](#-stockgro-simulation-results)
10. [🤔 Reflections & Improvements](#-reflections--improvements)
11. [💻 How to Run](#-how-to-run)
12. [📎 References & Links](#-references--links)

---

## 📌 Project Overview

This project was built as part of the Time Series Analysis capstone in collaboration with **StockGro**, a real-time stock market simulator. The goal was to apply time series forecasting to build a robust short-term trading strategy within a virtual portfolio of ₹10,00,000 and execute trades over a 2-day live competition window.

---

## 🎯 Objectives

- Forecast short-term stock prices using models like ARIMA, LSTM, and Prophet.
- Identify trends and volatility patterns to inform trading decisions.
- Construct a diversified and optimized portfolio.
- Evaluate performance through real trades on the StockGro platform.

---

## 📚 Methodology & Models

The following models and methods were used:

| Model                  | Purpose                                                    |
|------------------------|------------------------------------------------------------|
| ARIMA                  | Baseline time-series forecasting                          |
| Prophet                | Capturing seasonality and trends                          |
| LSTM                   | Learning complex temporal dependencies                     |
| GARCH                  | Modeling and forecasting volatility                        |
| Random Forest Regressor | Feature-based stock return prediction                    |
| Markowitz Optimization | Portfolio risk-return balancing via efficient frontier     |

---

## 📊 Stock Selection Rationale

Stocks were selected based on the following criteria:

- **Liquidity**: High daily trading volume.
- **Sector Diversification**: Tech, healthcare, consumer goods.
- **Growth Potential**: Historical upward momentum and analyst sentiment.
- **Low Volatility**: For minimizing portfolio risk.

---

## 🔍 Data Sources & Preprocessing

- Historical stock price data was sourced using the `yfinance` API.
- Time range: **Jan 1, 2020 – Dec 31, 2024**
- Preprocessing included:
  - Handling missing values (forward/backward fill)
  - Checking stationarity (ADF test)
  - Scaling data (for LSTM)
  - Creating training/test splits (last 6 months reserved for testing)

---

## 📈 Forecasting Strategy

Forecasted the next **2 trading days** for each stock using multiple models:

- **ARIMA**: Tuned using AIC/BIC, residuals analyzed
- **Prophet**: Included trend and seasonality components
- **LSTM**: Achieved high accuracy on non-linear data
- **Evaluation Metrics**:
  - RMSE
  - MAPE
  - Directional Accuracy

---

## 💼 Portfolio Construction

- Combined forecast signals to select top 3 stocks
- Allocation strategy:
  - Stock A: 40%
  - Stock B: 30%
  - Stock C: 30%
- Techniques used:
  - **Forecast-guided allocation**
  - **Volatility-aware sizing** (inverse weighting with GARCH volatility estimates)
  - **Sector-based diversification**

---

## 📉 Model Performance & Metrics

| Model   | RMSE  | MAPE (%) | Accuracy |
|---------|-------|-----------|----------|
| ARIMA   | 13.52 | 2.3%      | 76%      |
| Prophet | 11.98 | 1.9%      | 81%      |
| LSTM    | 10.12 | 1.5%      | 86%      |

Key Insight: **LSTM outperformed** others due to its ability to capture non-linear relationships.

---

## 📱 StockGro Simulation Results

- **Total Return**: +12.5%
- **Volatility (σ)**: 14% (vs. market average of 18%)
- Notable Trade: Stock A bought at ₹350 → exited at ₹378 (+8%)
- Avoided high-volatility stocks like Stock D

---

## 🤔 Reflections & Improvements

**What worked:**
- LSTM model captured nuanced trends
- Volatility-based sizing reduced overall risk
- Sector rotation helped maximize returns

**What didn’t:**
- ARIMA struggled with non-stationary and high-frequency noise
- Prophet had limited flexibility with abrupt market changes

**Improvements:**
- Include attention-based models (e.g., Transformers)
- Live retraining of models based on daily updates
- Incorporate macroeconomic sentiment data

---

## 💻 How to Run

1. Clone the repository
   ```bash
   git clone https://github.com/yourusername/stock-price-tsa.git
   cd stock-price-tsa

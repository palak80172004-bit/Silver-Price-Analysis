# Silver Price Analysis and Forecasting (2016–2026)

## Abstract

This research presents a comprehensive analysis and forecasting study of silver prices using historical market data from 2016 to 2026. The study integrates Exploratory Data Analysis (EDA), classical time-series techniques, and machine learning models to understand price behavior, volatility, seasonality, and future trends. Two forecasting approaches are evaluated: Facebook Prophet for time-series forecasting and a Random Forest regression model using engineered financial features. The results demonstrate that time-series-aware models capture long-term trends and seasonality effectively, while machine learning models provide insights into feature importance and short-term price dynamics. The final output includes a detailed forecast for Q1 2026, offering practical insights for investors, analysts, and researchers.

---

## 1. Introduction

Silver is a critical precious metal with applications in investment, industry, and technology. Its price is influenced by macroeconomic factors, industrial demand, inflation, currency strength, and market sentiment. Accurate forecasting of silver prices is therefore valuable for portfolio management, hedging strategies, and economic research.

This project aims to:

* Analyze historical silver price movements
* Identify trends, seasonality, and volatility patterns
* Engineer meaningful financial features
* Build and compare forecasting models
* Generate future price projections for Q1 2026

The complete analysis pipeline is implemented in Python and is fully reproducible.

---

## 2. Dataset Description

The dataset consists of daily silver price data with the following attributes:

* Date
* Open, High, Low, Close prices
* Price (target variable)
* Volume (removed due to missing values)

The data spans multiple years, covering thousands of trading days. Dates are parsed and set as the time-series index to enable temporal analysis.

Key preprocessing steps:

* Date conversion and indexing
* Removal of empty columns
* Missing value inspection
* Statistical summary generation

---

## 3. Exploratory Data Analysis (EDA)

EDA was conducted to understand the overall behavior of silver prices.

### 3.1 Price Trends

* Line plots show long-term upward and downward movements
* Periods of high volatility align with known global economic events

### 3.2 Distribution Analysis

* Histogram and box plots reveal price skewness and outliers
* Mean and median prices indicate distribution asymmetry during volatile periods

### 3.3 Yearly Analysis

* Year-wise aggregation highlights:

  * Average annual prices
  * Minimum and maximum price ranges
  * Annual volatility

Visualization of yearly averages helps identify macro trends and regime shifts.

---

## 4. Time Series Analysis

### 4.1 Moving Averages

Multiple moving averages (7, 30, 90, 365 days) were calculated to smooth short-term fluctuations and highlight long-term trends.

### 4.2 Seasonal Decomposition

A multiplicative seasonal decomposition was applied using a 252-day period (trading year), separating the series into:

* Trend
* Seasonal
* Residual components

This decomposition confirms the presence of seasonality and structural trends in silver prices.

### 4.3 Stationarity Test

The Augmented Dickey-Fuller (ADF) test indicates that the raw price series is non-stationary, justifying the use of advanced forecasting models capable of handling trends and seasonality.

---

## 5. Feature Engineering

To enhance predictive performance, several financial and temporal features were created:

* Daily Returns (%)
* Rolling Volatility (7-day, 30-day)
* Price Range (High − Low)
* Calendar features (Month, Day of Week, Quarter)
* Lag features (1, 7, 14, 30 days)

A correlation heatmap was generated to analyze relationships between key variables, revealing strong correlations among price-based features.

---

## 6. Forecasting Models

### 6.1 Prophet Time-Series Model

Facebook Prophet was used for primary forecasting due to its ability to model:

* Non-linear trends
* Weekly and yearly seasonality
* Structural changes via changepoints

The dataset was split into training (80%) and testing (20%) sets in chronological order.

**Evaluation Metrics:**

* RMSE
* MAE
* MAPE
* R² Score

Prophet demonstrated strong performance in capturing overall price movement and seasonal effects.

### 6.2 Random Forest Regression Model

A Random Forest Regressor was trained using engineered features to model price behavior as a supervised learning problem.

Steps:

* Feature selection
* Train-test split without shuffling
* Feature scaling using StandardScaler
* Model training and prediction

Feature importance analysis highlights the dominance of lagged prices, moving averages, and volatility measures.

---

## 7. Model Evaluation and Comparison

A comparative analysis was conducted using RMSE, MAE, and R² metrics:

* **Prophet** excels in long-term trend and seasonality forecasting
* **Random Forest** provides interpretability through feature importance and captures short-term patterns

Visual comparisons of actual vs. predicted values further validate model performance.

---

## 8. Future Forecast: Q1 2026

Using the Prophet model retrained on the full dataset, daily forecasts were generated for January–March 2026.

Outputs include:

* Predicted price
* Lower and upper confidence bounds
* Monthly aggregated statistics (average, minimum, maximum prices)

The forecast indicates moderate price stability with seasonal fluctuations during Q1 2026.

---

## 9. Market Insights

Additional analyses include:

* Year-over-Year (YoY) price growth
* Cumulative return analysis

These metrics provide a broader investment perspective and help contextualize the forecast within historical performance.

---

## 10. Conclusion

This research demonstrates a complete, end-to-end silver price forecasting framework combining statistical analysis, time-series modeling, and machine learning. Key takeaways:

* Silver prices exhibit strong trends, volatility clustering, and seasonality
* Prophet is well-suited for long-term forecasting
* Random Forest models add value through feature-driven insights
* The Q1 2026 forecast provides actionable intelligence for stakeholders

Future work may include incorporating macroeconomic indicators, deep learning models (LSTM), and scenario-based forecasting.

---

## 11. Reproducibility

* Language: Python
* Libraries: Pandas, NumPy, Matplotlib, Seaborn, Prophet, Scikit-learn, Statsmodels
* Output: CSV forecast file for Q1 2026

All code and results are fully reproducible and available in this GitHub repository.


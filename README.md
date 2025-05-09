# Macroeconomic-Informed-Market-Forecasting

🧠 Objective

This project was completed as part of a technical challenge for a final-round interview with Data Analysis Inc. (DAI). The goal was to build a predictive model that forecasts the 5-day forward log return (with a 1-day lag) of the NASDAQ index (NASDAQCOM), using only information available at the time of prediction.

🗃️ Data Sources

All economic indicators used are publicly available via:

- FRED (Federal Reserve Economic Data)

- ALFRED (Archival FRED) – used for indicators that are subject to revisions (e.g., CPI and Nonfarm Payrolls)

Predictors include:

- Effective Federal Funds Rate

- 2-Year Treasury Rate

- 10-Year Treasury Rate

- Nonfarm Payrolls (from ALFRED)

- Consumer Price Index (CPI-U, from ALFRED)

Volatility Index (VIX)

🔄 Prediction Target

The model aims to predict:

log(NASDAQ_t+5 / NASDAQ_t)

With a one-day lag for prediction execution (i.e., at time t-1, we use all available info to predict log_return(t, t+5)).

🧪 Modeling Approach
Data Preprocessing

- Removed zero values in NASDAQCOM (treated as NULLs)

- Used only data available at each point in time to avoid look-ahead bias

- Interpolated and aligned indicators with NASDAQ dates

Feature Engineering

- Created lagged versions of each macroeconomic indicator

- Standardized features

- Added temporal features (day of week, month, etc.)

Models Used

Baseline: Linear Regression, Ridge

Tree-based: XGBoost Regressor

Deep Learning: LSTM (Pytorch) for time-dependent modeling

Evaluation

Train-test split aligned with time series (no random shuffling)

Evaluated using RMSE, MAE

📊 Key Results
Linear regression achieved the lowest MAE.

XGBoost captured momentum patterns but was prone to overfitting.

Feature importance showed FRED and CPI were leading indicators.

🚀 Future Work
Incorporate additional lag structures and macro sentiment features.

Test rolling-window validation or walk-forward optimization.

Deploy the model via a REST API for real-time testing.

🛠️ Technologies Used
Python, pandas, NumPy, scikit-learn

XGBoost, Pytorch

matplotlib, seaborn

FRED/ALFRED API access via API

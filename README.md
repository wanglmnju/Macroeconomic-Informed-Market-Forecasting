# Macroeconomic-Informed-Market-Forecasting

Problem definition


Objective:
Predict 5-day forward log returns of the NASDAQ Composite Index using only economic time-series data that was available in real-time, with a focus on Federal Reserve indicators, Treasury yields, employment data, inflation, and market volatility.

Mathematically:

For each trading day 
, predict:

(6-day ahead price vs. 1-day ahead price, giving a 5-day forward return with 1-day lag)


Constraints:
No future data leakage
Must handle revised data using ALFRED
Treat zero values in NASDAQCOM as NULLs and drop them
Minimum Features: ["FEDFUNDS", "DGS2", "DGS10", "PAYEMS", "CPIAUCSL", "VIXCLS"]

Why This Matters:
Trading Strategy Development
Predict short-term market movements to inform tactical asset allocation or hedging decisions.

Macro-Risk Assessment
Quantify how Federal Reserve policy (rates), Treasury markets (yield curve), and economic health (NFP/CPI) impact tech stock performance.

Data Challenges
Real-world constraints: Avoid look-ahead bias by using only data available at prediction time (via ALFRED's vintage data).


Business Impact:
A successful model could:

For Asset Managers: Signal short-term rebalancing opportunities in tech-heavy portfolios.

For Risk Teams: Provide early warnings when macro conditions (e.g., yield curve inversion) predict NASDAQ drawdowns.

For DAI: Demonstrate how real-time economic data pipelines can generate alpha in systematic strategies.

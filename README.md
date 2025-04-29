📈 Pairs Trading with Cointegration and Z-Score Signal Strategy

This project demonstrates how to identify cointegrated stock pairs and generate trading signals using a rolling z-score strategy. The approach is based on statistical arbitrage, and the code is structured for backtesting with a 7-year training period and 3-year test period.

🧠 What This Project Does
📥 Downloads or processes historical price data for a list of stocks.
🔍 Identifies cointegrated pairs using the Engle-Granger cointegration test.
📊 Visualizes p-values using a heatmap to highlight strong statistical relationships.
⚙️ Computes price ratio between pairs.
📉 Calculates rolling moving averages (5-day and 60-day) and rolling standard deviation.
📐 Computes the z-score to detect mean reversion opportunities.
📈 Plots:
Ratio + MAs
Z-score with buy/sell signal thresholds
🧪 Methodology
Cointegration Detection
Uses statsmodels.tsa.stattools.coint() to test pairwise cointegration.
A p-value < 0.05 indicates strong cointegration.
Rolling Signal Calculation
Compute 5-day moving average of price ratio
Compare to 60-day moving average and std deviation
Z-score = (MA5 - MA60) / Std60
Signal Logic (to be implemented)
Buy if Z < -1 (undervalued)
Sell if Z > 1 (overvalued)
Close position when Z crosses 0

📦 Dependencies
Python 3.x
pandas
numpy
matplotlib
statsmodels

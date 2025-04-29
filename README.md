# 📈 Pairs Trading with Cointegration and Z-Score Strategy

This project demonstrates how to identify cointegrated stock pairs and generate trading signals using a rolling z-score strategy. The approach is based on statistical arbitrage, using historical price data and moving average comparisons.

---

## 🧠 What This Project Does

- 📥 Loads historical stock price data
- 🔍 Identifies **cointegrated pairs** using the Engle-Granger test
- 📊 Visualizes **p-values** using a heatmap
- ⚙️ Computes **price ratio** between two assets
- 📉 Calculates **rolling moving averages** (5-day & 60-day)
- 📐 Computes **z-score** for mean-reversion signals
- 📈 Plots:
  - Price ratio + MAs
  - Z-score with buy/sell signal thresholds

---

## 🧪 Methodology

1. **Cointegration Detection**
   - Uses `statsmodels.tsa.stattools.coint()` to test each pair
   - A p-value < 0.05 indicates strong cointegration

2. **Rolling Signal Calculation**
   - 5-day moving average (`MA5`) vs. 60-day moving average (`MA60`)
   - 60-day standard deviation
   - **Z-score** = `(MA5 - MA60) / Std60`

3. **Signal Logic (can be extended)**
   - **Buy** if Z < -1 (price ratio is undervalued)
   - **Sell** if Z > 1 (overvalued)
   - **Exit** when Z approaches 0 (mean reversion)

---

## 📦 Dependencies

Install required libraries:

```bash
pip install pandas numpy matplotlib statsmodels


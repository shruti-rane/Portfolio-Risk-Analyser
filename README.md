# Portfolio Risk Analyzer

## Overview
This project analyzes the risk characteristics of a multi-asset equity portfolio using historical market data.  
Instead of focusing on trading or return prediction, the goal is to **quantify portfolio risk, diversification benefits, and downside exposure**.

The analysis is performed on an equal-weight portfolio of large-cap US equities:
- Apple (AAPL)
- Microsoft (MSFT)
- Alphabet / Google (GOOGL)

Historical adjusted price data is sourced via Yahoo Finance.

---

## Objective
The project shows:

1. How a portfolio behaves when compared to holding individual stocks
2. Whether diversification reduces risk
3. How volatility, drawdowns, and correlations affect portfolio outcomes
4. What trade-offs exist between return and risk when combining assets

---

## Methodology

### 1. Data Collection
- Downloaded daily adjusted closing prices using `yfinance`
- Prices are adjusted for splits and dividends to ensure accurate return calculations
- Data is aligned by date across all assets

### 2. Return Computation
- Converted prices into daily percentage returns
- Returns are used instead of prices to enable fair comparison across assets

### 3. Portfolio Construction
- Constructed an **equal-weight portfolio** (1/3 per asset)
- Daily portfolio returns are computed as a weighted average of individual asset returns

### 4. Risk & Performance Analysis
The following metrics are computed for both the portfolio and each individual stock:

- **Final Equity**: Growth of \$1 invested over the period
- **Annualized Volatility**: Measures return variability (risk)
- **Sharpe Ratio**: Risk-adjusted return
- **Maximum Drawdown**: Worst peak-to-trough loss

### 5. Diversification Analysis
- Computed the correlation matrix between assets
- Compared portfolio behavior against individual stock performance
- Visualized normalized price performance and equity curves

---

## Key Financial Concepts Used

### Volatility
Volatility measures how much returns fluctuate over time.  
Lower volatility generally implies a smoother investment experience.

### Correlation
Correlation measures how similarly assets move:
- High correlation → limited diversification benefit
- Lower correlation → improved diversification

### Diversification
Combining multiple assets can reduce overall portfolio risk, but diversification benefits depend on correlation patterns and market conditions.

### Drawdown
Drawdown measures the decline from a historical peak to a subsequent trough.  
Maximum drawdown captures worst-case downside risk and is critical for understanding investor risk tolerance.

---

## Results Summary (2020–2025)

- The diversified portfolio exhibited **lower volatility** than some individual stocks
- The portfolio provided **smoother return behavior** compared to holding single assets
- However, the portfolio experienced a **larger maximum drawdown than Apple (AAPL)**

This result highlights a key financial insight:
> Diversification reduces average risk but does not guarantee a lower worst-case drawdown.

Overlapping drawdown periods across assets can lead to prolonged cumulative losses at the portfolio level.

---

## Key Takeaways
- Risk must be evaluated using multiple metrics, not returns alone
- Diversification is effective for volatility reduction but less reliable for drawdown control
- Portfolio-level risk behavior can differ meaningfully from individual asset behavior
- Correlation patterns during stress periods play a critical role in portfolio outcomes

---

## Tools & Libraries
- Python
- pandas
- numpy
- matplotlib
- yfinance

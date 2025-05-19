# Portfolio_Optimization
Construction of High-Risk and Low-Risk Investment Portfolios using current stock data

This project constructs two investment portfolios — one high-risk and one low-risk — using historical stock data and quantitative optimization techniques in Python. The project showcases two versions of the optimization:

1. **Without minimum weight constraints** — the optimizer is free to exclude any stock.
2. **With minimum weight constraints (5%)** — every stock must be included with at least 5% allocation.

---

## Objectives

- Construct a **High-Risk Portfolio** with higher expected return and greater volatility.
- Construct a **Low-Risk Portfolio** focused on stability, defensive sectors, and lower risk.
- Compare portfolio outcomes with and without diversification constraints.

---

## Methodology

- Collected daily stock data from Yahoo Finance using `yfinance`
- Computed:
  - Daily log returns
  - Annualized expected returns and volatility
  - Beta (vs SPY)
  - Trailing P/E ratios
- Maximized the **Sharpe Ratio** using `scipy.optimize.minimize`
- Applied different constraint sets to reflect high-risk vs low-risk profiles

---

## Optimization Constraints

###  High-Risk Portfolio:
- Volatility ≥ 20%
- Expected return ≥ 12%
- ≥ 30% allocation to TSLA, NVDA, GOOGL
- Weighted portfolio P/E ≥ 25
- (In Version 2) Minimum 5% weight per stock

###  Low-Risk Portfolio:
- Volatility ≤ 15%
- Expected return ≥ 6%
- ≤ 10% in TSLA and NVDA
- ≥ 40% allocation to KO, JNJ, PG, PEP
- Weighted portfolio P/E ≤ 20
- (In Version 2) Minimum 5% weight per stock

---

## Results Summary

| Version                      | High-Risk Return | High-Risk Volatility | Low-Risk Return | Low-Risk Volatility |
|-----------------------------|------------------|----------------------|-----------------|---------------------|
| Without Min Weights         | 33.77%           | 20.00%               | 18.49%          | 15.00%              |
| With Min Weights (5% each)  | 29.54%           | 20.00%               | 6.55%           | 13.28%              |

> Without minimum constraints, portfolios are more concentrated (e.g., TSLA gets 64.1%). With diversification enforced, weights are more balanced across all 10 stocks.

---

##  Files

- Code.ipynb: Python code for data processing, optimization, and analysis
- Report: pdf report of the project
- README.md — This file

---

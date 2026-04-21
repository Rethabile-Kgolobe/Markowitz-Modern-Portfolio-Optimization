# Portfolio Optimization using Markowitz Modern Portfolio Theory

##  Overview

This project implements **Modern Portfolio Theory (MPT)** to construct an optimal portfolio that maximizes the **Sharpe Ratio** using historical financial data.

The model evaluates the trade-off between **risk and return** and identifies the most efficient allocation of assets.

---

## Key Concepts

### 1. Log Returns

We compute daily log returns:

[
r_t = \ln\left(\frac{P_t}{P_{t-1}}\right)
]

---

### 2. Expected Return (Annualized)

[
\mu = 252 \cdot \text{mean}(r_t)
]

---

### 3. Covariance Matrix

[
\Sigma = 252 \cdot \text{cov}(r_t)
]

---

### 4. Portfolio Return

[
R_p = \mathbf{w}^T \boldsymbol{\mu}
]

---

### 5. Portfolio Risk (Volatility)

[
\sigma_p = \sqrt{\mathbf{w}^T \Sigma \mathbf{w}}
]

---

### 6. Sharpe Ratio

[
S = \frac{R_p}{\sigma_p}
]

---

## Optimization Problem

We solve:

[
\max_{\mathbf{w}} \frac{\mathbf{w}^T \boldsymbol{\mu}}{\sqrt{\mathbf{w}^T \Sigma \mathbf{w}}}
]

Subject to:

* (\sum w_i = 1)
* (0 \leq w_i \leq 1)

---

## ⚙️ Methodology

1. Collect historical price data using `yfinance`
2. Compute log returns
3. Estimate expected returns and covariance
4. Generate random portfolios (Monte Carlo simulation)
5. Optimize portfolio weights using **SLSQP**
6. Visualize the Efficient Frontier

---

## 📈 Assets Used

* Apple (AAPL)
* Amazon (AMZN)
* Tesla (TSLA)
* Walmart (WMT)
* S&P 500 ETF (SPY)
* Nasdaq ETF (QQQ)
* Gold ETF (GLD)

---

## 📊 Results

### Optimal Portfolio (Example)

* Return: ~20%
* Risk: ~14.7%
* Sharpe Ratio: ~1.37

### Key Insights

* Gold (GLD) had a high allocation due to low correlation with equities
* High-volatility assets like TSLA received smaller weights
* Broad ETFs (SPY, QQQ) were excluded due to redundancy

---

## Efficient Frontier

The Efficient Frontier shows the set of optimal portfolios offering the highest return for a given level of risk.

---


##  Data Source

Data was obtained using the `yfinance` library from Yahoo Finance.

This project is for **educational purposes only** and does not constitute financial advice.

---

##  Future Improvements

* Include risk-free rate (Capital Market Line)
* Add portfolio backtesting
* Build interactive dashboard (Streamlit)
* Add short-selling constraints

---

##  Author


Rethabile Kgolobe

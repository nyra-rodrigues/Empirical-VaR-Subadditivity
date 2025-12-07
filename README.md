# **VaR Subadditivity Failure — Empirical Analysis**

This repository contains the research PDF and supporting documentation for our project **“VaR Subadditivity Failure: Empirical Backtesting Across Assets and Portfolio Styles.”**
The work was conducted during Fall 2025 study term.

**Supervised by:** **Jingcheng Yu**
**Researchers:** Nyra Rodrigues, Cindy Yang, Wincy Huang, Yurim Song

---

## **Project Overview**

Value-at-Risk (VaR) is a widely used risk measure in portfolio management, but it fails to satisfy *subadditivity*—meaning that the VaR of a combined portfolio can be **higher** than the sum of its individual components. This can undermine diversification and lead to miscalibrated capital requirements.

Our project empirically investigates **when**, **how**, and **under what market conditions** VaR becomes unreliable or overly conservative.

We compare several forecasting methods and evaluate their breach behavior, shortfall severity, and adaptation speed during volatile periods.

The accompanying **PDF report** provides the full technical results, figures, and statistical tests.

---

## **What We Studied**

### **1. Individual Stock VaR Behavior**

We examined assets such as **SPY, XOM, IWM, and TSLA**, focusing on:

* 95% and 99% VaR forecasts
* Volatility clustering
* Breach timing during mini-crises
* Exceedance severity (capital shortfall when VaR fails)

Key insights include:

* **QR (Quantile Regression)** stays closest to the 5% target.
* **GJR-GARCH** is conservative but still exposes deep losses.
* **Historical Simulation (HS)** adapts too slowly when volatility jumps.

---

### **2. Portfolio Construction & Styles**

We formed multiple portfolios to test whether diversification makes VaR more stable:

* **Balanced:** SPY / QQQ / IWM
* **Value:** BRK-B / JPM / WMT
* **Growth / High ROE:** AAPL / MSFT / GOOGL
* **Stable earnings:** JNJ / PG / KO
* **High beta:** TSLA / QQQ / IWM
* **Small size:** INMD / CELH / PLUG

These portfolios allow us to observe whether VaR is more prone to failures in high-beta, size-tilted, or defensive structures.

---

### **3. Subadditivity Testing**

We compared:

* **Portfolio VaR**
  vs.
* **Sum of individual VaRs**

Using Kupiec tests and exceedance tracking, we identified conditions where VaR becomes:

* Non-subadditive
* Sensitive to market jumps
* Too conservative during calm periods
* Too slow to adjust during stress

---

## **Models Compared**

| Method  | Breach Rate (%) | Avg Shortfall (bp) | Max Shortfall (bp) | Severity Share (%) |
| ------- | --------------- | ------------------ | ------------------ | ------------------ |
| **GJR** | 3.96            | 133.9              | 1,021.6            | 26.7%              |
| **HS**  | 4.73            | 143.3              | 1,099.1            | 37.0%              |
| **QR**  | 5.33            | 120.5              | 1,095.1            | 36.3%              |

**Interpretation:**

* **QR**: best calibration + lowest average shortfall
* **GJR**: conservative but still hit hard during jumps
* **HS**: worst adaptation speed — highest severity during volatility spikes

---

## **Acknowledgments**

This research was completed under the supervision of **Jingcheng Yu**, with contributions from **Nyra Rodrigues**, **Cindy Yang**, **Wincy Huang**, and **Yurim Song**.
# SIAS Global Equity Risk & Performance Analysis

## Overview  
This repository contains a Python-based toolkit that empowers the SIAS Risk Team to compute a comprehensive suite of portfolio risk and performance metrics—without requiring direct access to the Bloomberg terminal. By simply pointing to the latest holdings files, you can reproduce volatility, drawdowns, Value-at-Risk, information ratios, and other key statistics for both the SIAS portfolio and its benchmark (iShares MSCI ACWI ETF).

## Features  
- **Comprehensive Risk Metrics**: Volatility, Sharpe, Sortino, max drawdown, Value-at-Risk (95%), Expected Shortfall (95%), beta, tracking error, information ratio, and more. 
- **Automated Data Ingestion:** : Reads the most recent SIAS asset-holdings Excel (BNY Mellon) and benchmark weights from the iShares ACWI ETF.
- **Interactive Analysis:**  IPython widgets enable on-the-fly sorting, filtering, and parameter selection directly in Jupyter/Colab.
- **Flexible Reporting:** Supports multiple lookback windows (1m, 3m, 6m, 12m) and custom evaluation horizons.
- **Benchmark Validation:** Built-in checks to compare against Bloomberg results for IPS accuracy and consistency.
- **Modular & Extensible:** Easy to add new metrics, swap benchmarks, or extend to other asset classes.

## Prerequisites  
1. **Python 3.8+**  
2. Core libraries:  
   - `pandas`  
   - `numpy`  
   - `scipy`
   - `statsmodels`
   - 'yahoo'
   - `pandas_datareader`  
   - `matplotlib` (for optional plotting)  
3. Interactive widgets:  
   - `ipywidgets`  

## Data Inputs

1. **SIAS Portfolio Holdings**

   * File format: `.xlsx` 
   * Source: BNY Mellon (latest file) by sfu email
         
2. **Benchmark Holdings & Weights**

   * File format: `.xlsx` or `.csv`
   * Source: iShares MSCI ACWI ETF ([product page](https://www.ishares.com/us/products/239600/ishares-msci-acwi-etf))

## Usage

1. **Clone or download** this repo.
2. **Open** the main analysis script (e.g., `risk_performance_analysis.py`) in your IDE, Jupyter, or Colab.
3. **Configure** the file paths at the top of the script:

   ```python
   SIAS_FILE       = "SIAS Asset Detail_dd mm yyyy.xlsx"
   BENCH_FILE      = "ACWI_holdings_dd mm yyyy.csv"
   ```
4. **Launch** the notebook or script.

   * The script will load and align portfolio vs. benchmark returns.
   * Interactive widgets allow you to adjust the analysis window and chart settings.
   * Generates a summary table and optional plots.`

## Verification & Quality Control

* **Bloomberg Cross-Check:** Run equivalent Bloomberg functions (e.g., `RV`, `RL`) for a spot check.
* **Versioning:** Tag scripts and data files with a date stamp (e.g., `2025-07-31`) to ensure reproducibility.

## Notebooks & Colab

Interactive implementation available on Google Colab:
[Open in Colab »](https://colab.research.google.com/drive/1l0Hvb7rZ-ynC90jzbVvXclNnZDeoaw8E?usp=sharing)

## Contributing

Feel free to submit pull requests or open issues for:

* New risk/attribution metrics
* Alternative data sources (e.g., WRDS, FactSet)
* Enhanced reporting templates

## Author & Contact

**Lili, Hui Gao**\
Risk and Compliance Portfolio Manager\
Student Investment Advisory Service (SIAS) — SFU\
2024 Cohort\
✉️ [hga87@sfu.ca](mailto:hga87@sfu.ca)

*Last Updated: July 31, 2025*

```
```

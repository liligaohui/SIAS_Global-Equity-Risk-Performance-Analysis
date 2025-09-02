# SIAS Global Equity Risk & Performance Analysis

## Overview

This repository provides a **Python-based toolkit** developed for the SIAS Risk Team to calculate a comprehensive suite of portfolio risk and performance metrics—**without requiring direct Bloomberg access**. By pointing the toolkit to the latest holdings files, users can reproduce key statistics such as volatility, drawdowns, Value-at-Risk, and information ratios for both the SIAS portfolio and its benchmark (**iShares MSCI ACWI ETF**).

## Features

* **Comprehensive Risk Metrics**: Volatility, Sharpe ratio, Sortino ratio, maximum drawdown, Value-at-Risk (95%), Expected Shortfall (95%), beta, tracking error, information ratio, and more.
* **Automated Data Ingestion**: Reads the most recent SIAS asset-holdings file (BNY Mellon) and benchmark weights (iShares MSCI ACWI ETF).
* **Interactive Analysis**: Built-in IPython widgets allow for on-the-fly sorting, filtering, and parameter adjustments directly in Jupyter/Colab.
* **Flexible Reporting**: Supports multiple lookback windows (1m, 3m, 6m, 12m) and custom evaluation horizons.
* **Benchmark Validation**: Includes checks against Bloomberg outputs to ensure consistency with IPS requirements.
* **Modular & Extensible**: Easy to extend with new metrics, swap benchmarks, or adapt for other asset classes.

## Prerequisites

1. **Python 3.8+**
2. Core libraries:

   * `pandas`
   * `numpy`
   * `scipy`
   * `statsmodels`
   * `yfinance`
   * `pandas_datareader`
   * `matplotlib` (for optional plots)
3. Interactive widgets:

   * `ipywidgets`

## Data Inputs

1. **SIAS Portfolio Holdings**

   * Format: `.xlsx`
   * Source: BNY Mellon (latest file delivered via SFU email)

2. **Benchmark Holdings & Weights**

   * Format: `.xlsx` or `.csv`
   * Source: iShares MSCI ACWI ETF ([Web Page](https://www.ishares.com/us/products/239600/ishares-msci-acwi-etf))

### Data Access
The dataset used in this project is not publicly available in this repository.  
A copy is hosted on Google Drive. To obtain access:

1. Visit the [Dataset Request Link](https://drive.google.com/drive/folders/14Qj5mYg8BhEvRLRt2MkeXgo4BZWTp-xB?usp=sharing).  
2. Submit an access request using your Google account.  
3. Access will be granted on a case-by-case basis for academic and research purposes.  

Note: Without this dataset, the analysis code will run but produce empty outputs or require substitution with your own data.

## Usage

1. **Clone or download** this repository.

2. **Open** the main analysis script (e.g., `risk_performance_analysis.py`) in Jupyter, Colab, or your preferred IDE.

3. **Configure** the file paths at the top of the script:

   ```python
   SIAS_FILE  = "yyyymmdd SIAS Asset Detail_dd mm yyyy.xlsx"
   BENCH_FILE = "ACWI_holdings_dd mm yyyy.csv"
   ```

4. **Run** the notebook or script:

   * The toolkit will load and align portfolio vs. benchmark returns.
   * Interactive widgets allow dynamic selection of lookback windows and chart settings.
   * Summary tables and optional plots will be generated automatically.

## Assumptions & Limitations

* **No look-through analysis**: Exposures are limited to directly held securities. Underlying fund or structured-product holdings are not decomposed.
* **Historical basis**: All metrics are calculated from historical return data without forward-looking adjustments or scenario modeling.
* **Static weights**: Portfolio weights are assumed to remain constant over the evaluation horizon (no rebalancing or trading effects are modeled).
* **USD reporting**: All calculations are expressed in U.S. dollars (USD). Currency translation effects may apply for non-USD securities.

## Verification & Quality Control

* **Bloomberg Cross-Check**: Results can be compared against Bloomberg functions (e.g., `RV`, `RL`) for validation.
* **Versioning**: Tag scripts and input files with a date stamp (e.g., `2025-07-31`) to maintain reproducibility.

## Notebooks & Colab

An interactive version of the toolkit is available on Google Colab:
[**Open in Colab »**](https://colab.research.google.com/drive/1l0Hvb7rZ-ynC90jzbVvXclNnZDeoaw8E?usp=sharing)

## Contributing

Contributions are welcome. Please open issues or submit pull requests for:

* New risk/attribution metrics
* Integration with alternative data sources (e.g., WRDS, FactSet)
* Enhanced reporting and visualization templates

## Author & Contact

**Lili Hui Gao**
Risk and Compliance Portfolio Manager
Student Investment Advisory Service (SIAS), SFU — 2024 Cohort
✉️ [hga87@sfu.ca](mailto:hga87@sfu.ca)

*Last updated: Sep 1, 2025*

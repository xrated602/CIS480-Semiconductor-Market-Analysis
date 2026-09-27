# CIS480 Semiconductor Market Analysis

## Historical Market Performance and Risk Analysis of Selected Semiconductor Stocks

**Course:** CIS480 Capstone  
**Team Members:** Luis Ramirez, Rey Guirette, and Colen Wilson

## Project Overview

This CIS480 capstone project compares the historical performance and risk of five semiconductor stocks with the broader U.S. market. The analysis covers January 1, 2021, through December 31, 2025.

The selected securities are:

- AMD — Advanced Micro Devices
- NVDA — NVIDIA
- INTC — Intel
- TSM — Taiwan Semiconductor Manufacturing Company (TSMC)
- AVGO — Broadcom
- SPY — SPDR S&P 500 ETF Trust, used as the benchmark

Our hypothetical stakeholder is a financial analyst or investment research team that needs a clear way to compare historical performance and risk across the selected securities.

This project is a historical comparison. It is not intended to predict future stock prices or provide investment recommendations.

## Research Questions

1. How did the cumulative returns of AMD, NVIDIA, Intel, TSMC, and Broadcom compare with SPY from 2021 through 2025?
2. How did the annualized volatility of AMD, NVIDIA, Intel, TSMC, and Broadcom compare with SPY from 2021 through 2025?
3. How did the maximum drawdown of AMD, NVIDIA, Intel, TSMC, and Broadcom compare with SPY from 2021 through 2025?

## Key Measures

The project uses three primary measures:

- **Cumulative Return %** — the percentage change in value over the selected historical period.
- **Annualized Volatility %** — a measure of how much daily returns varied, annualized using approximately 252 trading days per year.
- **Maximum Drawdown %** — the largest decline from a previous high during the selected period.

All six securities use the same analysis period and calculation methods so the results can be compared consistently.

## Technology and Workflow

The project uses:

- **yfinance** to retrieve historical market data
- **Python** for data preparation and calculations
- **Jupyter Notebook** for the reproducible analysis workflow
- **CSV files** for raw, cleaned, and derived project data
- **Power BI** for the interactive market performance and risk dashboard
- **GitHub** for project organization and version control

Project workflow:

`yfinance → Python/Jupyter Notebook → Data Validation → KPI Calculations → Processed Data → Power BI Dashboard`

## Analysis Build

The final master Jupyter Notebook provides an end-to-end analytical workflow from historical market data through validation and KPI calculations.

The analysis includes:

- Six securities: AMD, NVDA, INTC, TSM, AVGO, and SPY
- 1,255 trading dates
- 7,530 cleaned stock-date records
- Validation for required securities, closing-price availability, duplicate dates, and date coverage
- Cumulative return calculations
- Annualized volatility calculations
- Maximum drawdown calculations
- Processed datasets prepared for dashboard development
- KPI validation prior to Power BI visualization

## Validated KPI Results

| Security | Cumulative Return | Annualized Volatility | Maximum Drawdown |
|----------|------------------:|----------------------:|-----------------:|
| AMD | 132.03% | 52.41% | -65.45% |
| AVGO | 804.76% | 42.31% | -41.15% |
| INTC | -17.82% | 46.24% | -70.80% |
| NVDA | 1326.20% | 52.22% | -66.34% |
| TSM | 195.86% | 37.37% | -56.47% |
| SPY | 98.08% | 17.11% | -24.50% |

These results describe the selected 2021–2025 historical period only and should not be interpreted as predictions of future performance.

## Power BI Dashboard

The project includes an interactive Power BI dashboard titled:

**Semiconductor Market Performance & Risk**

The dashboard provides a visual comparison of the five semiconductor stocks and SPY across the three primary project measures.

Dashboard features include:

- **Date Range slicer** for selecting a historical analysis period
- **Security slicer** for selecting an individual security
- **Cumulative Return KPI card**
- **Annualized Volatility KPI card**
- **Maximum Drawdown KPI card**
- **Cumulative Return vs. SPY line chart**
- **Annualized Volatility comparison chart**
- **Maximum Drawdown comparison chart**

The KPI cards respond to the selected security and date range. The comparison charts display all six securities so users can compare the selected semiconductor stocks with the SPY benchmark.

The cumulative return chart rebases performance to the beginning of the selected date range, allowing securities to be compared from a common starting point.

## Team Responsibilities

### Rey Guirette — Data Architecture & Data Preparation

Rey is responsible for historical data retrieval and review, cleaning, organization, required-field checks, and preparation of the analysis-ready dataset.

### Colen Wilson — Python Analysis & Quality Validation

Colen is responsible for the Python calculations for cumulative return, annualized volatility, and maximum drawdown, along with analytical validation and quality checks.

### Luis Ramirez — Project Coordinator / Power BI & Business Analysis

Luis is responsible for project coordination, KPI and acceptance-criteria definitions, Power BI dashboard development, stakeholder usability, interpretation, documentation, and final project integration.

All three team members review the final project and supporting evidence.

## Repository Structure

```text
CIS480-Semiconductor-Market-Analysis/
├── README.md
├── data/
│   ├── raw/
│   │   └── CIS480_Raw_Stock_Data_2021_2025.csv
│   └── processed/
│       ├── cleaned_market_data_2021_2025.csv
│       ├── cleaned_market_data_formatted_2021_2025.csv
│       └── kpi_summary_metrics_2021_2025.csv
├── notebooks/
│   └── CIS480_Final_Master_Analysis.ipynb
└── powerbi/
    └── CIS480_Semiconductor_Market_Performance_Dashboard.pbix

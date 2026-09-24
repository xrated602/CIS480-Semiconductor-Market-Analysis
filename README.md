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
- **CSV files** for appropriate cleaned or derived project outputs
- **Power BI** for the planned final dashboard

Project workflow:

`yfinance → Python/Jupyter Notebook → Validation and KPI Calculations → Derived Outputs → Power BI Dashboard`

## First Working Build

The current Jupyter Notebook provides an end-to-end working path from historical market data to validated KPI results.

The first build includes:

- Six securities: AMD, NVDA, INTC, TSM, AVGO, and SPY
- 1,255 trading dates
- 7,530 cleaned stock-date records
- Validation for required securities, closing-price availability, duplicate dates, and date coverage
- Cumulative return calculations
- Annualized volatility calculations
- Maximum drawdown calculations

The A04 notebook validation status is **Passed**.

## Current KPI Results

| Security | Cumulative Return | Annualized Volatility | Maximum Drawdown |
|---|---:|---:|---:|
| AMD | 132.03% | 52.41% | -65.45% |
| AVGO | 804.76% | 42.31% | -41.15% |
| INTC | -17.82% | 46.24% | -70.80% |
| NVDA | 1326.20% | 52.22% | -66.34% |
| TSM | 195.86% | 37.37% | -56.47% |
| SPY | 98.08% | 17.11% | -24.50% |

These results describe the selected 2021–2025 historical period only and should not be interpreted as predictions of future performance.

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
├── notebooks/
│   └── CIS480_Historical_Stock_Analysis_A04.ipynb
├── outputs/
│   └── derived project outputs
├── powerbi/
│   └── Power BI project files
└── documentation/
    └── project reports and supporting documentation
```

Folders and files will be added as the project progresses.

## Running the Analysis

1. Open the Jupyter Notebook in the `notebooks` folder.
2. Install the required Python libraries if they are not already available.
3. Run the notebook cells in order from beginning to end.
4. Review the validation output before using the calculated results.
5. Confirm that all six securities are present and that the three KPI measures are produced for each security.

Additional environment and dependency details will be documented as the project repository is completed.

## Data Use

Historical market data is retrieved using yfinance. Downloaded source data should not be published in a public repository. This repository will focus on project code, documentation, and appropriate derived outputs while following applicable data-use requirements.

## Current Project Status

The Python/Jupyter analysis and A04 first working vertical slice are operational. The Power BI dashboard and final project documentation are still in development.

## Limitations

- The analysis covers only January 1, 2021, through December 31, 2025.
- The five selected companies do not represent the entire semiconductor industry.
- Cumulative return, annualized volatility, and maximum drawdown do not capture every aspect of investment performance or risk.
- SPY is a broad-market benchmark and does not control for every difference between individual semiconductor companies and the overall market.
- Historical results do not guarantee or predict future performance.
- The stakeholder is hypothetical, so no real stakeholder feedback is claimed unless actual testing occurs.

## Responsible AI Use

ChatGPT by OpenAI has been used as a support tool for organizing project ideas, reviewing assignment requirements, improving report structure and wording, and assisting with parts of the notebook workflow. The team reviews retained AI-assisted material against the project data, notebook output, and course requirements. AI-generated statements are not treated as evidence that the data or calculations are correct.

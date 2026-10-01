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
- **Power BI** for the final interactive dashboard
- **GitHub** for project organization and version control

Project workflow:

`yfinance → Python/Jupyter Notebook → Validation and KPI Calculations → Processed Data → Power BI Dashboard`

## Final Analysis Build

The final master Jupyter Notebook provides an end-to-end reproducible path from historical market data to validated KPI results.

The final analysis includes:

- Six securities: AMD, NVDA, INTC, TSM, AVGO, and SPY
- 1,255 trading dates
- 7,530 cleaned stock-date records
- Validation for required securities, closing-price availability, duplicate dates, and date coverage
- Cumulative return calculations
- Annualized volatility calculations
- Maximum drawdown calculations

The analysis validation status is **Passed**.

## KPI Results

| **Security** | **Cumulative Return** | **Annualized Volatility** | **Maximum Drawdown** |
| ------------ | --------------------: | ------------------------: | -------------------: |
| AMD          | 132.03%               | 52.41%                    | -65.45%              |
| AVGO         | 804.76%               | 42.31%                    | -41.15%              |
| INTC         | -17.82%               | 46.24%                    | -70.80%              |
| NVDA         | 1326.20%              | 52.22%                    | -66.34%              |
| TSM          | 195.86%               | 37.37%                    | -56.47%              |
| SPY          | 98.08%                | 17.11%                    | -24.50%              |

These results describe the selected 2021–2025 historical period only and should not be interpreted as predictions of future performance.

## Power BI Dashboard

The final Power BI dashboard provides an interactive view of the historical market analysis.

The dashboard includes:

- Date-range filtering
- Security selection
- Cumulative Return %
- Annualized Volatility %
- Maximum Drawdown %
- Cumulative return comparison with SPY
- Annualized volatility comparison across all six securities
- Maximum drawdown comparison across all six securities

The security selector allows the user to examine KPI results for an individual security while the comparison charts provide context across the five semiconductor stocks and SPY.

The final Power BI file is located in the `powerbi` folder.

## Team Responsibilities

### Rey Guirette — Data Architecture & Data Preparation

Rey was responsible for historical data retrieval and review, cleaning, organization, required-field checks, and preparation of the analysis-ready dataset.

### Colen Wilson — Python Analysis & Quality Validation

Colen was responsible for the Python calculations for cumulative return, annualized volatility, and maximum drawdown, along with analytical validation and quality checks.

### Luis Ramirez — Project Coordinator / Power BI & Business Analysis

Luis was responsible for project coordination, KPI and acceptance-criteria definitions, Power BI dashboard development, stakeholder usability, interpretation, documentation, and final project integration.

All three team members reviewed the project and supporting analysis.

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
├── docs/
│   ├── data_card.md
│   ├── data_dictionary.txt
│   ├── week05_validation_record.md
│   └── week05_work_plan_contribution_record.md
├── notebooks/
│   └── CIS480_Final_Master_Analysis.ipynb
└── powerbi/
    └── CIS480_Semiconductor_Market_Performance_Dashboard.pbix
```

The repository separates raw and processed data from the reproducible Jupyter analysis and final Power BI dashboard.

Individual team-member branches are maintained to preserve development history and individual contributions, while the `main` branch contains the final integrated project.

## Running the Analysis

1. Open `CIS480_Final_Master_Analysis.ipynb` from the `notebooks` folder.
2. Install the required Python libraries if they are not already available.
3. Run the notebook cells in order from beginning to end.
4. Review the validation output before using the calculated results.
5. Confirm that all six securities are present.
6. Confirm that cumulative return, annualized volatility, and maximum drawdown are produced for each security.
7. Review the processed CSV outputs in the `data/processed` folder.
8. Open the `.pbix` file in the `powerbi` folder to view the final interactive dashboard.

## Data Use

Historical market data was retrieved using yfinance for educational analysis. The repository contains the data and derived outputs used to support the CIS480 capstone analysis.

The project is intended for educational purposes and historical analysis only.


## Week 6 Methodology Architecture and Baseline

Week 6 documents the project's end-to-end analytical methodology and adds a reproducible baseline reconciliation test. The smallest complete pipeline path is:

`Yahoo Finance / yfinance → raw CSV snapshot → Python/Jupyter preprocessing → data-quality validation → KPI calculation → processed CSV → Power BI dashboard`

### Baseline and Evaluation

The Week 6 baseline independently recalculates SPY cumulative return from the first and last adjusted closing prices in the validated analytical dataset:

`(Ending Adjusted Close / Beginning Adjusted Close) - 1`

In the executed Week 6 notebook, the independent baseline is **98.084691%** and the pipeline result is **98.084691%**, producing an absolute difference of **0.0000000000** and a **PASSED** status. The executed notebook test compares the unrounded baseline with the pipeline result and passes when the absolute difference is no greater than **0.0001 as a proportion (0.01 percentage point)**.

Random cross-validation is not used because this is a descriptive dashboard project rather than a predictive model. Calculation reconciliation, data-quality checks, and reproducible dashboard tests are better matched to the project's claims.

### Reproducibility

1. Install the Python dependencies listed in `requirements.txt`.
2. Open `notebooks/CIS480_Final_Master_Analysis.ipynb`.
3. Run the notebook cells in order.
4. Confirm the Week 5 data-quality checks pass before interpreting KPI output.
5. Run the Week 6 SPY cumulative-return reconciliation test.
6. Confirm the independent baseline and pipeline result are within the stated tolerance.
7. Review the processed CSV outputs before refreshing or interpreting the Power BI dashboard.

The Week 6 test supports the tested SPY cumulative-return reconciliation only. It does not establish that every source value, every KPI, or every Power BI interaction is error-free, and historical results are not predictions of future performance.

### Week 6 Evidence

- `notebooks/CIS480_Final_Master_Analysis.ipynb` — executable methodology and baseline test
- `requirements.txt` — Python dependency list
- `docs/week06_architecture_diagram.png` — accessible architecture visual
- `docs/week06_baseline_validation_record.md` — input, expected result, actual result, decision rule, status, and limitations
- `docs/week06_work_plan_contribution_record.md` — owner, task, status, dependency, acceptance criterion, and contribution evidence


## Project Status

The core CIS480 market-analysis workflow is complete.

Completed project components include:

- Historical market-data preparation
- Data cleaning and validation
- Final integrated Jupyter Notebook
- KPI calculations and validation
- Processed analysis datasets
- Interactive Power BI dashboard
- GitHub repository organization
- Project README documentation

Additional course documentation may be added as the capstone progresses.

## Limitations

- The analysis covers only January 1, 2021, through December 31, 2025.
- The five selected semiconductor companies do not represent the entire semiconductor industry.
- Cumulative return, annualized volatility, and maximum drawdown do not capture every aspect of investment performance or risk.
- SPY is a broad-market benchmark and does not control for every difference between individual semiconductor companies and the overall market.
- Historical results do not guarantee or predict future performance.
- The stakeholder is hypothetical, so no real stakeholder feedback is claimed unless actual testing occurs.

## Responsible AI Use

ChatGPT by OpenAI was used as a support tool for organizing project ideas, reviewing assignment requirements, improving report structure and wording, assisting with portions of the notebook workflow, supporting Power BI dashboard development, and organizing the GitHub repository.

The team reviewed retained AI-assisted material against the project data, notebook output, and course requirements. AI-generated statements were not treated as evidence that the data or calculations were correct. Final project decisions, validation, interpretation, and submitted work remain the responsibility of the project team.

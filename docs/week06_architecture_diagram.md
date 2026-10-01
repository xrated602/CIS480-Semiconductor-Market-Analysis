# Week 6 Analytical Methodology Architecture

## Architecture diagram

```mermaid
flowchart LR
    A[Yahoo Finance / yfinance] --> B[Raw CSV Snapshot]
    B --> C[Python + Jupyter Preprocessing]
    C --> D[Data Quality Validation + KPI Calculation]
    D --> E[Processed Numerical CSV]
    E --> F[Power BI Dashboard]
```

**Figure 1. CIS480 analytical methodology architecture.**

**Text equivalent / alt description:** Public historical market data are retrieved through yfinance and preserved as a raw CSV snapshot. Python and Jupyter preprocess the data, validate quality, and calculate historical performance and risk KPIs. Numerical processed CSV outputs are then consumed by Power BI to provide the interactive historical comparison dashboard.

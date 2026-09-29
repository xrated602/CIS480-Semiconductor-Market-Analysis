# CIS480 Week 5 Data Card

## Dataset Identification
**Project:** Historical Market Performance and Risk Analysis of Selected Semiconductor Stocks  
**Dataset:** cleaned_market_data_2021_2025.csv  
**Coverage:** January 4, 2021 through December 31, 2025  
**Frequency:** Daily market trading observations  
**Securities:** AMD, AVGO, INTC, NVDA, TSM, and SPY  
**Unit of analysis:** One security on one trading date.

## Purpose and Intended Use
The dataset supports a historical comparison of five selected semiconductor stocks with SPY. The project evaluates cumulative return, annualized volatility, and maximum drawdown from 2021 through 2025. It is intended for the CIS480 capstone, Python analysis, validation, and Power BI visualization.

The dataset is not intended to predict future prices, recommend investments, or represent all semiconductor companies or market conditions.

## Source and Provenance
Historical market data was retrieved through the Python yfinance library from Yahoo Finance. The master notebook records the requested tickers, date range, daily interval, and auto-adjusted price setting. A raw snapshot was preserved before the data was reshaped and transformed.

Provenance chain:
Yahoo Finance market data -> yfinance retrieval -> preserved raw CSV -> Python preprocessing -> cleaned numerical CSV -> KPI calculations -> Power BI dashboard.

## Permission and Licensing Risk
Yahoo Finance is publicly accessible, but public accessibility does not by itself establish unrestricted redistribution rights for the underlying market data. Yahoo's published permissions guidance notes that third-party content, including stock quotes, may have separate rights, and Yahoo's terms restrict uses that exceed granted rights.

For this academic project, the data is used for educational analysis. The team should not claim that Yahoo Finance market data is open-licensed or freely redistributable unless that permission is independently established. Because redistribution rights for the underlying quotes are not established by the project evidence, this remains a documented permission risk. The repository should remain private for course use unless the team or instructor confirms that redistribution of the raw market-data snapshot is permitted.

## Dataset Composition
The executed Week 5 profile produced:
- 7,530 analytical rows
- 1,255 unique trading dates
- 6 securities
- 15 final fields
- 1,255 rows per security
- 0 duplicate Trading_Date + Ticker keys
- 0 missing Adj_Close values

The final fields are documented in docs/data_dictionary.txt.

## Preprocessing
The preprocessing workflow is reproducible in the master Jupyter notebook. Major steps include:
1. Retrieve daily historical data for the six securities.
2. Preserve the original downloaded dataset as a raw CSV snapshot.
3. Reshape the source data into a long analytical format with one ticker-date observation per row.
4. Retain observations with a valid adjusted closing price.
5. Calculate Daily_Return, Cumulative_Return, Rolling_Peak, and Drawdown.
6. Add Ticker, Company, and Asset_Class fields.
7. Calculate Trading_Day_Count, Normalized_Price, Benchmark_Difference, Year, and Annual_Return.
8. Validate schema, ticker coverage, key uniqueness, missingness, and logical value ranges.
9. Export the numerical dataset and presentation-formatted dataset separately.

## Missingness
The Week 5 profile found 6 missing Daily_Return values and 6 missing Benchmark_Difference values. These are expected structural missing values: the first observation for each of the six securities has no prior observation from which to calculate Daily_Return, and Benchmark_Difference depends on Daily_Return.

These values are retained as missing rather than imputed as zero because zero would imply an observed return that did not occur.

## Data Quality and Validation
The executed Week 5 validation passed the expected schema, required-security coverage, composite-key uniqueness, adjusted-price completeness, structural-missingness checks, and logical range checks.

Observed extreme values are not automatically removed using an arbitrary threshold. They are retained unless source evidence shows that a value is erroneous.

## Sensitive or Restricted Information
The analytical dataset contains historical security-market observations and calculated fields. It does not contain student records, private contacts, credentials, account numbers, or personally identifiable information.

The main data-governance concern is not personal information but permission to redistribute source-derived market data.

## Known Limitations and Unknowns
The analysis covers only five selected semiconductor companies and SPY during 2021-2025, so findings should not be generalized to all semiconductor stocks or future periods. SPY is a broad-market benchmark rather than a semiconductor-specific index. Results depend on the source data and the project's preprocessing and metric definitions.

The project evidence supports the observed row counts, missingness, ticker coverage, calculations, and validation results. It does not establish that Yahoo Finance or its underlying providers grant unrestricted redistribution rights for the raw historical quote data. That permission remains unknown unless separately confirmed.

## Maintenance and Versioning
This dataset is treated as a fixed historical project snapshot for the 2021-2025 analysis. The raw snapshot should remain unchanged so the analysis can be reproduced. If the yfinance retrieval is rerun later, source values or library behavior could change; a rerun should therefore be treated as a new dataset version and revalidated before replacing project outputs.

## Related Evidence
- notebooks/CIS480_Final_Master_Analysis.ipynb — retrieval, preprocessing, KPI calculations, and Week 5 validation
- docs/data_dictionary.txt — field definitions and data-quality notes
- data/processed/cleaned_market_data_2021_2025.csv — primary numerical analytical dataset
- data/processed/cleaned_market_data_formatted_2021_2025.csv — presentation-formatted dataset
- data/processed/kpi_summary_metrics_2021_2025.csv — KPI summary

## Week 5 Decision
The final analytical dataset passed the implemented data-quality checks and is suitable for the project's historical analysis and Power BI dashboard. The team will preserve structural missing values, avoid arbitrary outlier deletion, preserve the raw snapshot for reproducibility, and document the unresolved redistribution-permission risk rather than assuming public availability equals an open license.

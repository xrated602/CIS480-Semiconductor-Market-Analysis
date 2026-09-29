# Week 5 Data Quality Validation Record

## Project
**Historical Market Performance and Risk Analysis of Selected Semiconductor Stocks**

**Validation artifact:** `notebooks/CIS480_Final_Master_Analysis.ipynb`  
**Dataset:** `cleaned_market_data_2021_2025.csv`  
**Validation scope:** Final analytical dataset used for Python analysis and the Power BI dashboard.

## Validation Question
Does the final analytical dataset meet the team's documented requirements for schema, row and security coverage, key uniqueness, missingness, and logical value ranges before it is used for KPI calculations and Power BI?

## Baseline and Acceptance Rule
The dataset is expected to contain the six required securities (AMD, AVGO, INTC, NVDA, SPY, and TSM) across the 2021-2025 project period and contain the fields required by the final analysis.

The Week 5 validation passes when:
- the expected schema is present;
- all six required securities are represented;
- the composite key `Trading_Date + Ticker` contains no duplicates;
- `Adj_Close` contains no missing values;
- missing `Daily_Return` and `Benchmark_Difference` values are limited to the expected first observation for each security;
- implemented logical range checks pass.

A failed check requires review before the affected data is treated as validated.

## Test Record

| Test | Input / Question | Expected Result | Actual Result | Status | Evidence |
|---|---|---|---|---|---|
| Schema | Does the final analytical dataframe contain the expected analysis fields? | 15 expected fields | 15 expected fields present | PASS | Master notebook, Week 5 Data Quality Profile |
| Row count | How many observations are in the final long-format dataset? | Six securities represented across the available trading dates | 7,530 rows | PASS | Master notebook, Week 5 Data Quality Profile |
| Trading-date coverage | Does the dataset cover the available project trading period? | Historical observations within the 2021-2025 project window | 1,255 unique trading dates; first 2021-01-04; last 2025-12-31 | PASS | Master notebook, Week 5 Data Quality Profile |
| Security coverage | Are all required securities present? | AMD, AVGO, INTC, NVDA, SPY, TSM | All six present | PASS | Master notebook, required-security check |
| Record count by security | Is coverage balanced across the six securities? | Review counts for unexpected gaps | 1,255 observations for each security | PASS | Master notebook, records-by-security profile |
| Composite-key uniqueness | Is each `Trading_Date + Ticker` pair unique? | 0 duplicate composite keys | 0 duplicates | PASS | Master notebook, ticker + date key uniqueness check |
| Adjusted-price completeness | Are adjusted closing prices available for every final observation? | 0 missing `Adj_Close` values | 0 missing values | PASS | Master notebook, missingness profile/final checks |
| Daily-return missingness | Are missing daily returns limited to structurally expected observations? | 6 missing values: one first observation per security | 6 missing values | PASS | Master notebook, missingness profile |
| Benchmark-difference missingness | Are missing benchmark differences limited to structurally expected observations? | 6 missing values because the first daily return is unavailable for each security | 6 missing values | PASS | Master notebook, missingness profile |
| Adjusted-price range | Are all adjusted closing prices positive? | `Adj_Close > 0` | Check passed | PASS | Master notebook, range and validity checks |
| Volume range | Are reported volumes nonnegative? | `Volume >= 0` | Check passed | PASS | Master notebook, range and validity checks |
| Daily-return sanity check | Do non-missing daily returns remain above a total loss of 100% in one observation? | `Daily_Return > -1` | Check passed | PASS | Master notebook, range and validity checks |
| Drawdown range | Are non-missing drawdowns zero or negative? | `Drawdown <= 0` | Check passed | PASS | Master notebook, range and validity checks |
| Normalized-price range | Are normalized prices positive? | `Normalized_Price > 0` | Check passed | PASS | Master notebook, range and validity checks |
| Trading-day sequence | Are trading-day indices valid? | `Trading_Day_Count >= 1` | Check passed | PASS | Master notebook, range and validity checks |
| Year range | Are derived years within the defined project period? | 2021 through 2025 | Check passed | PASS | Master notebook, range and validity checks |

## Missing-Value Decision
The six missing `Daily_Return` values are retained as missing because the first observation for each security has no previous observation from which to calculate a return. The six corresponding missing `Benchmark_Difference` values are also retained because that field depends on `Daily_Return`.

The team does not replace these values with zero. Doing so would imply that a measured zero return occurred when the value is actually unavailable because of the calculation boundary.

## Outlier Decision
The profile reports observed numeric ranges but does not automatically remove unusually large or small market movements. The team did not establish a source-supported threshold that would make an extreme market return invalid. Therefore, an extreme observation is retained unless source evidence shows that it is erroneous.

This prevents the preprocessing step from introducing bias by deleting valid market movements simply because they are unusual.

## Validation Result
**Final Week 5 data quality status: PASS.**

The executed notebook supports using the final analytical dataset for the project's historical KPI calculations and Power BI dashboard under the implemented checks.

## Limitations and Unknowns
A passing validation result means the dataset passed the checks implemented by the team; it does not prove that every source value is error-free. The validation checks internal structure, completeness of required adjusted-price observations, expected missingness, uniqueness, security coverage, and logical ranges.

The project also does not establish unrestricted redistribution rights for the underlying Yahoo Finance market data. That issue is documented separately in `docs/data_card.md`.

The results apply to this specific 2021-2025 dataset version and the six securities included in the project. If the source data is retrieved again or the preprocessing rules change, the validation should be rerun.

## Decision
Based on the executed tests, the team accepts the cleaned dataset for the current historical analysis. Structural missing values will remain missing, extreme observations will not be removed without evidence that they are erroneous, and any new or revised dataset version must pass the validation checks before replacing the current analytical dataset.

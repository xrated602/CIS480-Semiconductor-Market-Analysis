# Week 8 — Demo and Acceptance Validation Record

**Status:** In progress. No Week 8 tests are represented as executed until actual outputs are recorded.

| ID | Input / question | Expected result / decision rule | Actual result | Status | Evidence link |
|---|---|---|---|---|---|
| W08-01 | Run frozen notebook with authorized 2021–2025 input | AMD, AVGO, INTC, NVDA, TSM and SPY present; 1,255 trading dates / 7,530 security-date rows if using existing snapshot; no duplicate security-date pairs or missing required closing prices | Not rerun for Week 8 | Pending | [Week 7 notebook](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/notebooks/CIS480_Final_Master_Analysis_W07.ipynb) |
| W08-02 | Independently recalculate SPY cumulative return on frozen snapshot | Difference from pipeline <= 0.0001 proportion (0.01 percentage point) | Prior Week 6 record: 98.084691% vs 98.084691%; Week 8 rerun pending | Pending | [Week 6 baseline record](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/docs/week06_baseline_validation_record.md) |
| W08-03 | Independently recalculate NVDA annualized volatility | Difference <= 0.0001 percentage points | Prior Week 7 record: 52.2246661252% independent and pipeline; Week 8 rerun pending | Pending | [Week 7 validation CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/week07_validation_record.csv) |
| W08-04 | Open Power BI file, select each of six securities, filter date, inspect three KPI measures | Filters and visuals agree with frozen processed CSV and show meaningful labels | Not tested for Week 8 | Pending | [Power BI folder](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/tree/main/powerbi) |
| W08-05 | Open repository and evidence links in signed-out browser | README, notebook, data, dashboard download and report accessible without credentials | Not checked | Pending | [Repository](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis) |
| W08-06 | Replay demo from frozen commit and authorized input | Presenter can reproduce narrative and fallback recording/text outline is available | Not tested | Pending | To be linked |
| W08-07 | Review files for secrets, personal paths, credentials and restricted data | No prohibited material in submitted package | Not checked | Pending | To be linked |

**Evidence boundary:** Existing saved outputs are prior-week evidence. A Week 8 PASS requires a dated rerun or direct inspection with actual results and a link. Historical comparisons are descriptive, not predictive.

## W08-08 — Six-security cumulative-return reconciliation (2026-10-12)

**Input:** Committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv), blob SHA `201523b1dfb57f80e9a11be0706af4862e6e0252`; fields `Start_Price`, `End_Price`, `Cumulative_Return`.

**Independent check:** For each row calculate `(End_Price / Start_Price) - 1` and compare with stored `Cumulative_Return`. **Expected:** all six tickers present and absolute difference <= 0.0001 as a proportion. **Actual:** all six present; each difference was 0 to displayed precision in a direct numeric recalculation. **Status: PASS** for internal arithmetic consistency only.

| Ticker | Independent return (%) | Stored return (%) | Status |
|---|---:|---:|---|
| AMD | 132.025998 | 132.025998 | PASS |
| AVGO | 804.763057 | 804.763057 | PASS |
| INTC | -17.822747 | -17.822747 | PASS |
| NVDA | 1326.197954 | 1326.197954 | PASS |
| SPY | 98.084726 | 98.084726 | PASS |
| TSM | 195.859208 | 195.859208 | PASS |

**Reproducible procedure:** Open the committed KPI CSV; for each row compute `float(End_Price)/float(Start_Price)-1` and compare to `float(Cumulative_Return)`. No data redownload is needed. The committed file is the test input and evidence; the record above contains dated actual outputs.

**Limitation:** This is a mathematical consistency check of a derived summary, not an independent validation of Yahoo Finance source prices, adjusted-price choices, full notebook execution, or dashboard behavior. The Week 6 SPY result (98.084691%) differs slightly from the current summary (98.084726%); this small difference is below the stated Week 6 tolerance but the snapshot/version provenance should be confirmed before calling them identical datasets.

## W08-09 — Saved notebook structure inspection (2026-10-12)

**Input:** [Week 7 executed notebook](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/notebooks/CIS480_Final_Master_Analysis_W07.ipynb), blob SHA `41eea667dd07b60fd00201d386a3cb9859caadb3`.

**Expected:** Notebook is inspectable JSON with code and saved outputs; all code cells have execution counts; no saved Python error outputs; data-quality and risk calculations present.

**Actual:** 41 total cells, including 22 code cells; all 22 code cells have execution counts 1–22; zero saved `error` outputs. Source contains data-quality checks, six-security KPI calculation, SPY return reconciliation, NVDA volatility reconciliation and CSV exports. **Status: PASS for static saved-notebook inspection only.**

**Limitations:** Static inspection does not prove that a fresh execution succeeds, that downloaded prices are unchanged, that saved outputs match the current committed CSVs, or that the PBIX works. The notebook fetches market data live with `yf.download`; an offline deterministic demo should instead use a frozen authorized input snapshot. A new Week 8 runtime test remains pending.

## W08-04 — User-confirmed dashboard smoke test (2026-10-12)

**Input / question:** Does the existing Power BI Desktop dashboard load, and do its filters work?

**Expected:** Dashboard opens without an apparent failure; slicer/filter interactions respond.

**Actual:** Luis reported, “Yes they do,” in response to the question, “Does your dashboard load correctly, and do the filters work?”

**Status: PASS — user-reported basic smoke test only.** This confirmation is not a direct assistant inspection of the PBIX, does not establish that every security was individually selected, and does not validate the displayed KPI values against the committed CSV. Full six-security, three-KPI reconciliation and screenshot or recording evidence remain **PENDING**.

**Evidence:** User confirmation in the project conversation, 2026-10-12. Add an inspectable screenshot/recording or GitHub review comment before final submission if required by the rubric.

### W08-04 follow-up confirmation (2026-10-12)

**User-reported actual result:** Luis confirmed all six securities (AMD, AVGO, INTC, NVDA, TSM, SPY) appear and all three KPI visuals display values, in addition to the prior confirmation that the dashboard loads and filters respond.

**Status:** PASS for user-reported dashboard display and interaction smoke test. **Pending:** independently compare dashboard figures for cumulative return, annualized volatility, and maximum drawdown against the frozen KPI summary CSV, and attach inspectable screenshot/recording evidence. No claim of numerical reconciliation or independent PBIX inspection is made.

### W08-04 NVDA KPI numeric reconciliation (2026-10-12)

**Input/question:** With NVDA selected in Power BI, do the three displayed KPIs match the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) after rounding to two decimal percentage points?

| KPI | Expected from committed CSV | Actual reported by Luis from Power BI | Status |
|---|---:|---:|---|
| Cumulative return | 1326.20% | 1326.20% | PASS |
| Annualized volatility | 52.22% | 52.22% | PASS |
| Maximum drawdown | -66.34% | -66.34% | PASS |

**Decision rule:** Exact equality at two displayed decimal places. **Actual:** All three match. **Status: PASS — user-reported NVDA numerical reconciliation.**

**Evidence boundary:** CSV is committed and inspectable; Power BI values were reported by the user in conversation rather than captured by an independent PBIX inspection or screenshot. Checks of the other five tickers and filter-dependent recalculation remain pending.

### W08-04 AVGO KPI numeric reconciliation (2026-10-12)

**Input/question:** With AVGO selected in Power BI, do three displayed KPIs match the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) rounded to two decimal places?

| KPI | Expected from committed CSV | Actual reported by Luis from Power BI | Status |
|---|---:|---:|---|
| Cumulative return | 804.76% | 804.76% | PASS |
| Annualized volatility | 42.31% | 42.31% | PASS |
| Maximum drawdown | -41.15% | -41.15% | PASS |

**Decision rule:** Equality at two displayed decimal places. **Status: PASS — user-reported AVGO numerical reconciliation.** CSV evidence is inspectable; Power BI values were supplied in conversation, not independently observed. Other tickers and date-filter recalculation remain pending.

### W08-04 AMD KPI numeric reconciliation (2026-10-12)

**Input/question:** With AMD selected in Power BI, do the three displayed KPIs match the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) rounded to two decimal places?

| KPI | Expected from committed CSV | Actual reported by Luis from Power BI | Status |
|---|---:|---:|---|
| Cumulative return | 132.03% | 132.03% | PASS |
| Annualized volatility | 52.41% | 52.41% | PASS |
| Maximum drawdown | -65.45% | -65.45% | PASS |

**Decision rule:** Equality at two displayed decimal places. **Status: PASS — user-reported AMD numerical reconciliation.** CSV evidence is inspectable; Power BI values were supplied in conversation, not independently observed. INTC, TSM and SPY and date-filter recalculation remain pending.

### W08-04 INTC KPI numeric reconciliation (2026-10-12)

**Input/question:** With INTC selected in Power BI, do the three displayed KPIs match the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) rounded to two decimal places?

| KPI | Expected from committed CSV | Actual reported by Luis from Power BI | Status |
|---|---:|---:|---|
| Cumulative return | -17.82% | -17.82% | PASS |
| Annualized volatility | 46.24% | 46.24% | PASS |
| Maximum drawdown | -70.80% | -70.80% | PASS |

**Decision rule:** Equality at two displayed decimal places. **Status: PASS — user-reported INTC numerical reconciliation.** CSV evidence is inspectable; Power BI values were supplied in conversation, not independently observed. TSM, SPY and date-filter recalculation remain pending. **Progress: 12/18 security-KPI combinations reconciled.**

### W08-04 TSM cumulative return discrepancy (2026-10-12)

**Input/question:** With TSM selected in Power BI, does cumulative return equal the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) at two decimal places?

**Expected:** 195.86%. **User-reported actual:** 198.86%. **Difference:** +3.00 percentage points. **Status: FAIL / needs investigation (provisional, pending recheck).**

**Next action:** Ask Luis to recheck the displayed TSM value and active date/slicer filters. If 198.86% is confirmed, compare the PBIX data snapshot and measure definition to the committed KPI summary. Do not edit source data to force a match. No conclusion about cause yet. TSM volatility and maximum drawdown are not yet checked.

### W08-04 TSM cumulative return correction (2026-10-12)

Luis clarified that the previously reported 198.86% was a **typing error**. The actual displayed TSM cumulative return in Power BI is **195.86%**, matching the committed KPI summary CSV **195.86%** at two decimal places. **Final status for TSM cumulative return: PASS (user-reported).** The preceding provisional mismatch is retained as an audit trail but is resolved; it is not evidence of a dashboard defect. TSM volatility and maximum drawdown are still pending.

### W08-04 TSM KPI numeric reconciliation (2026-10-12)

**Input/question:** With TSM selected in Power BI, do all three displayed KPIs match the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) rounded to two decimal places?

| KPI | Expected from committed CSV | Actual reported by Luis from Power BI | Status |
|---|---:|---:|---|
| Cumulative return | 195.86% | 195.86% (corrected typo) | PASS |
| Annualized volatility | 37.37% | 37.37% | PASS |
| Maximum drawdown | -56.47% | -56.47% | PASS |

**Decision rule:** Equality at two displayed decimal places. **Status: PASS — user-reported TSM numerical reconciliation.** The earlier 198.86% entry was explicitly corrected as a typo; it is not a dashboard mismatch. CSV evidence is inspectable; PBIX values were supplied in conversation, not independently observed. SPY and date-filter recalculation remain pending. **Progress: 15/18 security-KPI combinations reconciled.**

### W08-04 SPY KPI reconciliation and full-period summary (2026-10-12)

**Input/question:** With SPY selected in Power BI, do all three KPI values match the committed [KPI summary CSV](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/data/processed/kpi_summary_metrics_2021_2025.csv) rounded to two decimal places?

| KPI | Expected from CSV | Actual reported by Luis from Power BI | Status |
|---|---:|---:|---|
| Cumulative return | 98.08% | 98.08% | PASS |
| Annualized volatility | 17.11% | 17.11% | PASS |
| Maximum drawdown | -24.50% | -24.50% | PASS |

**Decision rule:** Exact match to two displayed decimal places. **Status: PASS — user-reported SPY numerical reconciliation.**

**Aggregate status:** 18/18 full-period, two-decimal KPI comparisons passed across AMD, AVGO, INTC, NVDA, TSM and SPY. The results were supplied by Luis from Power BI and compared to committed CSV values; no screenshot or independent PBIX execution was obtained. Date-filtered KPI behavior, fresh frozen-input notebook execution, signed-out access, and team approvals remain pending. This is a PASS for full-period user-reported visual-to-CSV numeric agreement only, not complete Week 8 demo acceptance.

### W08-04 date-slicer interaction check (2026-10-12)

**Input/question:** After clearing individual stock selection and changing the date slicer from the full 2021–2025 window to 2024 only, do cumulative return, annualized volatility, and maximum drawdown visuals respond?

**Expected:** All three KPI visuals update when the date window changes.

**Actual:** Luis reported “They all update.” **Status: PASS — user-reported date-filter responsiveness.**

**Evidence boundary:** This confirms visible interaction, not that each metric is mathematically recomputed with a correct 2024-only denominator or rolling/peak reset. Numeric 2024-specific cross-check against a separate filtered calculation remains pending, as does screenshot/recording evidence.

### W08-04 2024 date-filtered NVDA return reconciliation (2026-10-12)

**Input:** Power BI date slicer 2024-01-01 through 2024-12-31, NVIDIA (NVDA) selected. **Expected:** 178.87% from the saved [Week 7 notebook calendar-year sensitivity table](https://github.com/xrated602/CIS480-Semiconductor-Market-Analysis/blob/main/notebooks/CIS480_Final_Master_Analysis_W07.ipynb), computed as the last 2024 adjusted closing price divided by the first 2024 adjusted closing price, minus one. **Actual:** Luis reported **178.87%** for NVIDIA with that date range. **Decision rule:** Equal to two displayed decimal places. **Status: PASS — user-reported filtered NVDA cumulative-return agreement.**

**Clarification:** A previous 25.59% report matches the notebook's 2024 SPY result, not NVDA; after revisiting the selection, Luis explicitly confirmed NVDA = 178.87%. The initial ambiguous observation is superseded for this test. The specific cause of the earlier 25.59% report was not established. This check does not validate date-filtered volatility or maximum drawdown.

### W08-05 2024 NVDA volatility and maximum drawdown independently verified (2026-10-12)

**Evidence:** User-uploaded `cleaned_market_data_2021_2025(8).csv`, 7,530 rows, 14 columns; 252 NVDA trading-date rows from 2024-01-02 to 2024-12-31. Compared to user-reported Power BI slicer selection NVDA, 2024-01-01 through 2024-12-31.

| KPI | Power BI (user-reported) | Independent CSV calculation | Status |
|---|---:|---:|---|
| Cumulative Return | 178.87% | 178.8740902933% | PASS |
| Annualized Volatility | 52.50% | 52.5033157950% | PASS |
| Maximum Drawdown | -27.05% | -27.0467681658% | PASS |

**Method:** Cumulative return = last 2024 adjusted close / first 2024 adjusted close - 1. Volatility = sample standard deviation of all 252 saved `Daily_Return` values for NVDA in 2024 times sqrt(252); this includes the January 2 return relative to the preceding trading day in 2023. Drawdown = minimum of (2024 adjusted close / cumulative maximum adjusted close *within the 2024 window* - 1). The independently recomputed 2024 maximum drawdown also equals the minimum saved `Drawdown` within that window. **Acceptance:** agreement to 2 displayed decimal places. **Outcome:** All 3 PASS. **Scope:** These are user-reported Power BI visual readings reconciled against an independently computed CSV result, not direct inspection of the PBIX. Other tickers' date-filtered calculations and fresh pipeline execution remain untested.

### W08-06 2024 AMD ticker-selection cumulative-return check (2026-10-12)

**Filter:** 2024-01-01 through 2024-12-31; switched ticker selection from NVDA to AMD. **Power BI:** user reported **-12.84%** cumulative return. **Independent reference:** saved Week 7 notebook `week7_annual` 2024 within-year return for AMD **-12.84%**, based on first and last 2024 adjusted closes. **Acceptance:** matches to two displayed decimal places. **Status: PASS (user-reported visual vs saved notebook).** This does not independently validate AMD's 2024 volatility or maximum drawdown.

### W08-07 2024 AMD annualized-volatility check (2026-10-12)

**Filter:** AMD, 2024-01-01 to 2024-12-31. **Power BI (user-reported):** 47.88%. **Independent calculation:** 47.8791324062%, from 252 AMD daily-return rows in user-uploaded `cleaned_market_data_2021_2025(8).csv`, using sample standard deviation of `Daily_Return` times sqrt(252). **Acceptance:** matches to two decimal places. **Status: PASS.** AMD 2024 maximum drawdown remains to be checked.

### W08-08 AMD 2024 drawdown (2026-10-12)

AMD, 2024-01-01 through 2024-12-31. Power BI user-reported: -43.76%. Independently recalculated from 252 AMD adjusted closing prices in the uploaded cleaned market CSV: -43.7600555836%, using the minimum of (adjusted close / running peak within 2024 - 1). PASS at two decimal places. All three AMD 2024 KPI comparisons now pass. Dashboard readings are user-reported.

### W08-09 AVGO 2024 cumulative return (2026-10-12)

Power BI selection: AVGO (Broadcom), date range 2024-01-01 through 2024-12-31. User-reported cumulative return: 116.48%. Reference: saved Week 7 notebook's within-year adjusted-close return for AVGO in 2024: 116.48%. Acceptance: matches to two decimal places. Status: PASS. Volatility and maximum drawdown for AVGO in 2024 remain untested.

### W08-10 AVGO 2024 annualized volatility (2026-10-12)

Power BI: AVGO selected, 2024-01-01 through 2024-12-31. User-reported annualized volatility: 53.92%. Independent calculation from 252 AVGO 2024 Daily_Return observations in uploaded cleaned market CSV: sample standard deviation times square root of 252 = 53.91512879899315%. Agreement to two displayed decimal places: PASS. AVGO 2024 maximum drawdown remains pending.

### W08-11 AVGO 2024 maximum drawdown (2026-10-12)

Power BI selection: AVGO, 2024-01-01 through 2024-12-31. User-reported maximum drawdown: -25.25%. Independently recalculated from 252 AVGO adjusted-close observations in uploaded cleaned market data: minimum of (adjusted close / running 2024 maximum adjusted close - 1) = -25.2529135579%. Matches to two displayed decimal places: PASS. All three AVGO 2024 KPI comparisons now pass. Power BI readings remain user-reported rather than direct PBIX inspection.

### W08-12 INTC 2024 cumulative return (2026-10-12)

Power BI selection: INTC (Intel), date range 2024-01-01 through 2024-12-31. User-reported cumulative return: -57.49%. Reference: saved Week 7 notebook's 2024 within-year adjusted-close return for INTC: -57.49%. Acceptance: agreement to two displayed decimal places. Status: PASS. INTC 2024 volatility and maximum drawdown remain pending.

### W08-13 INTC 2024 annualized volatility (2026-10-12)

Power BI selection: INTC, 2024-01-01 through 2024-12-31. User-reported annualized volatility: 51.18%. Independently recalculated from 252 INTC 2024 Daily_Return rows in user-uploaded cleaned market CSV: sample standard deviation times square root of 252 = 51.17681454796064%. Acceptance: agreement to two displayed decimal places. Status: PASS. INTC 2024 maximum drawdown remains pending.

### W08-14 INTC 2024 maximum drawdown (2026-10-12)

Power BI selection: INTC, 2024-01-01 through 2024-12-31. User-reported maximum drawdown: -61.37%. Independent calculation from the uploaded cleaned market CSV, 252 INTC adjusted closing prices during 2024: minimum of (adjusted close / cumulative maximum adjusted close reset within 2024 - 1) = -61.3663180515%. Acceptance: matches to two displayed decimal places. Status: PASS. Important: the precomputed full-history Drawdown column has a different minimum (-69.5732%) in this window because its peak is anchored to the entire history; use the window-reset drawdown for this comparison. All three INTC 2024 KPI comparisons now pass.

### W08-15 TSM 2024 cumulative return (2026-10-12)

Power BI selection: TSM (Taiwan Semiconductor), 2024-01-01 through 2024-12-31. User-reported cumulative return: 97.27%. Independent reference: saved Week 7 notebook's 2024 within-year adjusted-close return for TSM: 97.27%. Acceptance: agreement to two displayed decimal places. Status: PASS. TSM 2024 annualized volatility and maximum drawdown remain pending.

### W08-16 TSM 2024 annualized volatility (2026-10-12)

Power BI selection: TSM, 2024-01-01 through 2024-12-31. User-reported annualized volatility: 40.50%. Independent calculation using the uploaded cleaned market CSV: 252 TSM 2024 Daily_Return observations; sample standard deviation (ddof=1) multiplied by sqrt(252) = 40.49505734357134%. Acceptance: matches to two displayed decimal places. Status: PASS. TSM 2024 maximum drawdown remains pending.

### W08-17 TSM 2024 maximum drawdown (2026-10-12)

Power BI: TSM selected, date slicer 2024-01-01 through 2024-12-31. User-reported maximum drawdown: -22.56%. Independent calculation from 252 TSM 2024 adjusted-close observations in the uploaded cleaned market CSV: minimum of (adjusted close / cumulative running maximum of adjusted close within 2024 - 1) = -22.559547444840554%. Agreement to two displayed decimal places: PASS. All three 2024 KPI comparisons for TSM now pass. All five semiconductor tickers (AMD, AVGO, INTC, NVDA, TSM) have now passed their three 2024 filtered KPI comparisons; SPY 2024 remains to be tested separately.

### W08-18 SPY 2024 cumulative return (2026-10-12)

Power BI selection: SPY benchmark, 2024-01-01 through 2024-12-31. User-reported cumulative return: 25.59%. Independent reference: saved Week 7 notebook's within-year adjusted-close return for SPY in 2024: 25.59%. Acceptance: agreement to two displayed decimal places. Status: PASS. SPY 2024 annualized volatility and maximum drawdown remain pending.

### W08-19 SPY 2024 annualized volatility (2026-10-12)

Power BI selection: SPY, date range 2024-01-01 through 2024-12-31. User-reported annualized volatility: 12.57%. Independent computation using 252 SPY Daily_Return observations in the user-uploaded cleaned market CSV: sample standard deviation (ddof=1) times sqrt(252) = 12.568977829844236%. Acceptance: matches to two displayed decimal places. Status: PASS. SPY 2024 maximum drawdown remains pending.

### W08-20 SPY 2024 maximum drawdown and six-ticker completion (2026-10-12)

Power BI selection: SPY benchmark, date range 2024-01-01 through 2024-12-31. User-reported maximum drawdown: -8.41%. Independent calculation from the uploaded `cleaned_market_data_2021_2025(8).csv`: 252 SPY adjusted-close rows for 2024; minimum of (adjusted close / running maximum adjusted close *within 2024* - 1) = -8.405618253124114%, reached on 2024-08-05. Agreement to two displayed decimal places: PASS. All three SPY 2024 KPI checks now pass.

**2024 date-filtered KPI milestone:** All 18 comparisons (6 tickers AMD, AVGO, INTC, NVDA, TSM, SPY times 3 metrics: cumulative return, annualized volatility, maximum drawdown) passed to two displayed decimal places, comparing user-reported Power BI values to saved notebook or independently calculated uploaded CSV values. The 18 full-period KPI comparisons also previously passed. These tests do not constitute fresh end-to-end notebook execution or direct inspection of the PBIX file.

### W08-21 Fresh Jupyter notebook execution (2026-10-12)

User opened `notebooks/CIS480_Final_Master_Analysis.ipynb` in local Jupyter and performed a restart-kernel/run-all-cells test as instructed. User reported: 'The notebook executed successfully.' **Status: PASS (user-reported fresh local execution)**. This supports reproducibility in the user's current environment, but is not an independent clean-environment test, and execution outputs, logs, dependency versions, and the exact input file state were not captured. Next: capture reproducibility evidence and verify required inputs/setup instructions for a separate reviewer.

### W08-22 Executed master notebook uploaded to GitHub (2026-10-12)

User reported uploading the saved, freshly executed `notebooks/CIS480_Final_Master_Analysis.ipynb` after running all cells in Jupyter. Verified directly by fetching the file from the public GitHub repository: blob SHA `a3dc3b5b32a6f87c97a2bbc4f6b282022d8d6331`, 16 code cells, all 16 have non-null execution counts, and no saved outputs of type `error`. **Status: PASS for uploaded execution evidence.** Note that saved output inspection does not by itself prove clean-environment reproducibility or that every output is correct; fresh execution was user-reported in W08-21.

### W08-23 Signed-out submission landing page access (2026-10-12)

**Input/question:** Can a reviewer open the [Week 8 submission landing page](week08_submission_package.md) without being signed in to GitHub? **Expected:** The page is readable in a signed-out/private browser session without authentication. **Actual:** Luis reported testing the link in an Incognito window and answered **Yes**, it opened. **Status: PASS (user-reported signed-out access for the landing page only).** **Evidence:** [Week 8 submission package](week08_submission_package.md) and this dated test statement. **Limitation:** This does not verify that every linked notebook, CSV, PBIX download, or other artifact is accessible without signing in. Those links require separate checks.

### W08-24 Signed-out master notebook viewing (2026-10-12)

**Input/question:** Can a reviewer view the [final master Jupyter notebook](../notebooks/CIS480_Final_Master_Analysis.ipynb) without signing into GitHub? **Expected:** The notebook page is viewable in a signed-out/private browser session. **Actual:** Luis reported **Yes** after being asked to open the notebook while still in Incognito mode. **Status: PASS (user-reported signed-out notebook page access).** **Evidence:** [Final master notebook](../notebooks/CIS480_Final_Master_Analysis.ipynb) and this dated test statement. **Limitation:** This verifies viewing the notebook page, not independently downloading/running it or access to all other evidence files.

### W08-25 Signed-out KPI summary CSV access (2026-10-12)

**Input/question:** Can a reviewer view the [processed KPI summary CSV](../data/processed/kpi_summary_metrics_2021_2025.csv) without signing into GitHub? **Expected:** CSV data is visible in a signed-out/private browser session. **Actual:** Luis reported **Yes** when asked to open the CSV in Incognito mode. **Status: PASS (user-reported signed-out CSV viewing).** **Evidence:** [Processed KPI summary CSV](../data/processed/kpi_summary_metrics_2021_2025.csv) and this dated record. **Limitation:** Does not confirm access to the cleaned-data CSV, PBIX download, or all other linked evidence.

### W08-26 Signed-out cleaned market data CSV access (2026-10-12)

**Input/question:** Can a reviewer view the [cleaned market data CSV](../data/processed/cleaned_market_data_2021_2025.csv) without signing into GitHub? **Expected:** CSV data visible in a signed-out/private browser session. **Actual:** Luis reported **Yes** while checking the CSV in Incognito mode. **Status: PASS (user-reported signed-out viewing).** **Evidence:** [Cleaned market data CSV](../data/processed/cleaned_market_data_2021_2025.csv) and this dated record. **Limitation:** Does not establish that the PBIX download or remaining links are publicly accessible.

### W08-27 Signed-out Power BI dashboard download option (2026-10-12)

**Input/question:** Can a reviewer access the [Power BI dashboard PBIX GitHub page](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) and see its download option without signing into GitHub? **Expected:** Public PBIX file page and download option available to signed-out visitors. **Actual:** Luis reported **Yes** after testing in Incognito mode. **Status: PASS (user-reported signed-out page and download-option access).** **Evidence:** [Power BI PBIX file](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) and this dated record. **Limitation:** Download completion and opening the PBIX in Power BI Desktop have not been independently verified by this test.

### W08-28 Signed-out Power BI PBIX download completion (2026-10-12)

**Input/question:** Can a reviewer download the [Power BI dashboard PBIX](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) while signed out of GitHub? **Expected:** File downloads successfully without authentication. **Actual:** Luis reported **Yes** after clicking Download in Incognito mode. **Status: PASS (user-reported signed-out download completion).** **Evidence:** [Power BI PBIX](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) and this dated record. **Limitation:** This test does not establish that the downloaded PBIX opens in Power BI Desktop or reproduces the expected visuals; those require a separate opening and functional check.

### W08-29 Downloaded PBIX opens in Power BI Desktop (2026-10-12)

**Input/question:** Can the publicly downloaded [Power BI dashboard PBIX](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) open in Power BI Desktop without requiring the reviewer to sign into the owner's Microsoft account? **Expected:** The file opens and dashboard is viewable after optional sign-in prompt is dismissed. **Actual:** Luis reported that Power BI initially asked for sign-in; after being instructed to dismiss the prompt, he confirmed **'It works.'** **Status: PASS (user-reported opening after dismissing sign-in prompt).** **Evidence:** [Power BI PBIX](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) and this dated test statement. **Limitations:** This is not Colen's independent PBIX functional review; individual visual/slicer/KPI behavior and another machine's environment have not been established by this test. Power BI Desktop may still prompt users to sign in.

### W08-30 Signed-out M08 PowerPoint download (2026-10-12)

**Input/question:** Can a reviewer download the [M08 team presentation](CIS480_M08_Demo_Day_Team_Presentation.pptx) from the Week 8 submission package without signing into GitHub? **Expected:** Public presentation link permits download without authentication. **Actual:** Luis reported **Yes** after opening the presentation link in an Incognito window and downloading it. **Status: PASS (user-reported signed-out PowerPoint download).** **Evidence:** [M08 team PowerPoint](CIS480_M08_Demo_Day_Team_Presentation.pptx) and [Week 8 submission package](week08_submission_package.md). **Limitation:** This does not independently verify that the downloaded PowerPoint opens correctly or that the backup walkthrough is available.

### W08-31 Downloaded M08 PowerPoint opens with speaker notes (2026-10-12)

**Input/question:** Does the publicly downloaded [M08 team presentation](CIS480_M08_Demo_Day_Team_Presentation.pptx) open in PowerPoint with slides and speaker notes visible? **Expected:** Presentation opens and speaker notes can be viewed. **Actual:** Luis answered **Yes** after being asked to open the downloaded presentation and check the slides and notes. **Status: PASS (user-reported local opening and speaker-note visibility).** **Evidence:** [M08 team PowerPoint](CIS480_M08_Demo_Day_Team_Presentation.pptx) and this dated test statement. **Limitation:** This does not establish that a backup walkthrough recording has been created, or that every team member has approved the presentation.

## W08-10 — Rey's independent notebook and documentation review (2026-10-13)

**Reviewer and input:** Rey Guirette; `notebooks/CIS480_Final_Master_Analysis.ipynb` run in Google Colab and Anaconda Jupyter; README, methodology and Week 8 documentation reviewed. Source: Rey's three-page PDF emailed to Luis October 13. [Structured evidence summary](week08_rey_independent_review_2026-10-13.md).

**Expected result:** Notebook runs successfully in both environments without missing dependencies, loads data, exports expected files; setup and methodology documentation are understandable.

**Actual reported result:** Rey reports **PASS** in both environments, no errors or missing dependencies, and successful raw/cleaned/formatted/KPI file exports. He reports that the README and repository links are sufficient and that the methodology, risk register, validation record, work plan and demo outline need no corrections.

**Status:** **PASS — teammate-reported independent execution and documentation review**. This supersedes the *not rerun for Week 8* statement in the initial W08-01 summary row **for the specific two-environment notebook smoke test**; it does not certify frozen-input deterministic reproducibility or all numeric reconciliation tests. The original PDF's screenshots show exported files, not full execution logs. **Evidence link:** [Rey's October 13 review summary](week08_rey_independent_review_2026-10-13.md). **Original PDF:** pending upload to repository or attachment to Canvas. Other outstanding acceptance checks remain pending.

## W08-11 — Colen's independent Power BI and documentation review (2026-10-15)

**Reviewer/input:** Colen Wilson independently reviewed the PBIX dashboard, findings and Week 8 documents. Source: five-page *Colens Week 8 Tasks.pdf* supplied by Luis (original PDF awaiting repository upload). **Expected:** Dashboard opens; all AMD, AVGO, INTC, NVDA, TSM and SPY appear; date and ticker selections update the relevant KPI cards and visuals consistently; no confusing cross-filter interactions.

**Actual:** **PASS** for opening, six securities displayed, date slicer, chart labels, and documented findings. **FAIL / unresolved** for ticker slicer-to-KPI card interactions: cards did not update consistently when individual stocks were selected; Colen reports KPI changes occurred when clicking stocks in charts, and clicking a different stock in a chart could clear KPI values. Colen also asked what 'All' means with no ticker selected. **Status: REVIEW COMPLETE — DASHBOARD INTERACTION DEFECT OPEN; NOT A FULL ACCEPTANCE PASS.**

**Usability recommendations:** Rename 'Cumulative Return vs SPY' card to 'Cumulative Return' unless SPY is consistently displayed; place stock slicer before date slicer; consider increasing cumulative-return chart height. **Documentation review:** Colen reported no corrections needed to validation, contribution, impact-risk and demo-outline files. **Interpretation:** NVDA strongest cumulative return (1326.20%), INTC weakest (-17.82%); semiconductor volatility and drawdowns exceed SPY; historical outcomes do not predict future performance. **Evidence:** Original five-page review PDF (to be uploaded); Power BI artifact [PBIX](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix). **Next test:** Reproduce ticker/card and chart-selection conflicts, correct filter interactions or clearly document intended behavior, then retest and capture expected/actual values. Colen's review does not constitute final team approval.

### W08-11 design clarification — 2026-10-16 (Luis)

Luis clarified the intended Power BI interaction model: **Date slicer filters both KPI cards and charts; Security slicer filters KPI cards only; charts retain all six securities for comparison over the chosen dates.** Accordingly, Colen's finding that ticker selection does not filter the charts is **expected behavior**, not itself a defect. Colen separately reported that conflicting chart selections could blank KPI cards; this behavior remains to be reproduced and assessed. **Status: Design clarified; chart-selection blank-card behavior pending assessment.** Update the dashboard instructions/demo to explain the intentional slicer scope. Do not interpret this clarification as proof that every Security slicer-to-card selection works correctly.

### W08-12 — Cumulative Return chart-to-KPI interaction retest (2026-10-16)

**Input/action:** Luis set Cumulative Return line chart interactions with the three KPI cards to **None** in Power BI Desktop. With full 2021–2025 dates and AMD selected in the Security slicer, he clicked NVDA in the Cumulative Return chart. **Expected:** KPI cards remain on AMD: cumulative return 132.03%, annualized volatility 52.41%, maximum drawdown -65.45%. **Actual:** Luis confirmed **Yes**, all three remained visible with AMD's values. **Status: PASS — user-reported local retest of the Cumulative Return chart only.** **Limitations:** The annualized-volatility and maximum-drawdown chart click interactions have not yet been retested; the edited PBIX has not yet been saved/re-uploaded to GitHub. The Security slicer intentionally controls KPI cards only, while Date controls both cards and charts.

### W08-13 — Bar-chart-to-KPI retest and cross-chart behavior (2026-10-16)

**Input/action:** With AMD selected in the Security slicer, Luis clicked NVDA in the Annualized Volatility and Maximum Drawdown bar charts after setting chart-to-KPI interactions to None. **Expected:** All three KPI cards continue displaying AMD. **Actual:** Luis confirmed **Yes**, the cards retained AMD values. **Status: PASS — user-reported local retest for both bar charts.** **Additional observation:** Clicking NVIDIA in the Cumulative Return chart also changes the Annualized Volatility and Maximum Drawdown charts to NVIDIA, while the KPI cards remain on AMD. This cross-chart interaction is not yet classified as desired or undesired; document the distinct card and chart selection scopes, or disable chart-to-chart interactions if independent comparison is the intended behavior. **Limitations:** Revised PBIX is still local and has not been verified after GitHub re-upload.

### W08-14 — Final chart-interaction configuration local test (2026-10-16)

**Input/action:** Luis configured the three comparison charts (Cumulative Return, Annualized Volatility, Maximum Drawdown) to have **None** interactions with one another and previously set chart-to-KPI interactions to None. Security slicer is intentionally scoped to KPI cards; Date slicer is intended to affect cards and charts. Luis reported making the changes and testing them. **Expected:** Clicking a security in any comparison chart leaves all six securities displayed in the other charts and does not change the Security slicer's KPI cards; Date slicer continues controlling all visuals. **Actual:** Luis confirmed the changes were made and tested, without supplying a separate step-by-step observation for each visual. **Status: PASS — user-reported local interaction test; detailed visual-by-visual evidence not independently inspected.** **Outstanding:** Save revised PBIX, upload it to the repository, confirm public download/opening, and obtain teammate review of the revised artifact before claiming final approval.

### W08-15 — Corrected Power BI artifact uploaded (2026-10-16)

**Input/action:** Luis reported saving the locally tested PBIX with revised chart interactions and uploading it via the GitHub website to `powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix`. **Expected:** Updated PBIX exists at the original repository path so evidence links remain valid. **Actual:** GitHub fetch confirmed the PBIX exists at the expected path, blob SHA `0fe0e319bebc4679646c17cdee880c0df41aa189`. **Status: PASS — repository file existence/path; corrected interaction behavior in the downloaded artifact not yet independently retested.** **Next:** Download this GitHub version, open it in Power BI Desktop, confirm intended Date/Security/chart interactions, and request Colen's recheck if feasible.

### W08-16 — Downloaded GitHub PBIX chart-interaction regression (2026-10-16)

**Tester:** Luis (user-reported test in Power BI Desktop after downloading the PBIX from GitHub). **Setup:** Security slicer AMD; click NVIDIA separately in each of the three charts. **Expected:** KPI cards remain on AMD; the other two charts retain all six securities. **Results:** Cumulative Return — PASS; Annualized Volatility — PASS; Maximum Drawdown — PASS. In the selected chart, NVIDIA becomes the active selection, as intended. **Overall status: PASS for all three chart-interaction checks on the downloaded repository artifact.** This addresses the unexpected cross-filtering/card-blanking behavior raised in Colen's review. **Not yet verified:** Colen's independent retest of the revised PBIX and final team signoff.

### Week 8 review closure decision — 2026-10-16

Luis elected not to request a second review from Colen. Colen's initial independent review remains on record; Luis implemented the recommended dashboard interaction changes and completed three PASS regression tests against the downloaded GitHub PBIX. **Disposition:** Interaction issue closed based on Luis's documented remediation and validation. **Scope:** This is not a claim that Colen independently retested or signed off on the corrected PBIX. Continue with remaining Week 8 submission and demo tasks.

### W08-17 — Signed-out submission landing-page access (2026-10-16)

**Tester:** Luis (user-reported). **Method:** Opened the Week 8 submission package URL in Chrome Incognito while signed out of GitHub. **Expected:** Landing page publicly visible without credentials. **Actual:** Luis confirmed the package and its links were visible. **Status: PASS for landing-page visibility.** This does not independently confirm that each linked binary artifact downloads or opens; verify those separately.

### W08-18 — Signed-out Jupyter notebook access (2026-10-16)

**Tester:** Luis (user-reported). **Method:** From the Week 8 package in Chrome Incognito, opened the Final master Jupyter notebook link without signing in to GitHub. **Expected:** Notebook publicly viewable. **Actual:** Luis confirmed GitHub displayed the notebook without requesting login. **Status: PASS for signed-out notebook visibility.** This is not a fresh notebook execution test.

### W08-19 — Signed-out corrected PBIX download access (2026-10-16)

**Tester:** Luis (user-reported). **Method:** In Chrome Incognito, followed the Power BI dashboard file link from the Week 8 submission package and downloaded the PBIX without signing in. **Expected:** Public download permitted. **Actual:** Luis confirmed download without login. **Status: PASS for signed-out PBIX download.** The downloaded repository copy's visual interactions were separately tested in W08-16.

### W08-20 — Signed-out M08 presentation download access (2026-10-16)

**Tester:** Luis (user-reported). **Method:** Followed the M08 team PowerPoint presentation link from the Week 8 submission package in Chrome Incognito, signed out of GitHub. **Expected:** Presentation downloadable without credentials. **Actual:** Luis confirmed successful public download. **Status: PASS for signed-out PowerPoint download.** This check does not establish accessibility or completeness of presentation content.

### W08-21 — Signed-out Section 6 report access (2026-10-16)

**Tester:** Luis (user-reported). **Method:** Opened Section 6 working report from Week 8 submission package in Chrome Incognito, signed out of GitHub. **Expected:** Report publicly readable. **Actual:** Luis confirmed report opened without requesting sign-in. **Status: PASS for signed-out Section 6 report access.**

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

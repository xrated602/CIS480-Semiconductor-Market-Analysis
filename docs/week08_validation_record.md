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

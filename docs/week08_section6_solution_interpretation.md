# Section 6 — Solution Interpretation, Impact, and Demo Day

**CIS480 Semiconductor Market Analysis | Week 8 working report | 2026-10-12**  
**Team:** Luis Ramirez, Rey Guirette, Colen Wilson  
**Status:** Draft for team review; independent teammate verification, demo freeze, recording, signed-out checks and final approval remain pending.

## Project question and audience

How did the cumulative returns, annualized volatility, and maximum drawdowns of AMD, AVGO, INTC, NVDA, and TSM compare with SPY from January 2021 through December 2025? Our hypothetical audience is an analyst who wants an inspectable historical comparison of performance and risk, not a price forecast or investment recommendation.

## Solution and inspectable evidence

We use a documented workflow: historical market prices retrieved through yfinance, a saved analytical CSV, Python/Jupyter data checks and KPI calculations, processed KPI outputs, and an interactive Power BI dashboard. The project includes six securities (five semiconductor stocks plus the broad-market SPY benchmark), 1,255 trading dates and 7,530 security-date observations in the documented dataset.

- [Executed master notebook](../notebooks/CIS480_Final_Master_Analysis.ipynb): inspect the calculations and saved outputs.
- [Cleaned historical input](../data/processed/cleaned_market_data_2021_2025.csv): inspect the analytical observations.
- [KPI summary CSV](../data/processed/kpi_summary_metrics_2021_2025.csv): inspect the exact derived metrics.
- [Power BI dashboard](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix): interactive visual artifact (requires Power BI Desktop).
- [Dated Week 8 validation record](week08_validation_record.md): questions, expected results, actual results, decisions and evidence.

## Findings and interpretation

| Security | Cumulative return | Annualized volatility | Maximum drawdown |
|---|---:|---:|---:|
| AMD | 132.03% | 52.41% | -65.45% |
| AVGO | 804.76% | 42.31% | -41.15% |
| INTC | -17.82% | 46.24% | -70.80% |
| NVDA | 1326.20% | 52.22% | -66.34% |
| TSM | 195.86% | 37.37% | -56.47% |
| SPY | 98.08% | 17.11% | -24.50% |

*Table description:* Full-period historical returns and two risk measures for five semiconductor securities and the SPY benchmark. Negative maximum drawdown values indicate losses from a prior peak; they are not cumulative returns.

NVDA had the highest cumulative return (1,326.20%), followed by AVGO (804.76%). INTC was the only selected security with a negative cumulative return (-17.82%). SPY's cumulative return was 98.08%, lower than four of the five selected semiconductor securities. These are **historical comparisons**, not evidence that the same rankings will persist.

Risk changes the interpretation. All five semiconductor stocks had higher annualized volatility than SPY (17.11%) and deeper maximum drawdowns than SPY (-24.50%). NVDA's high return coincided with 52.22% annualized volatility and a -66.34% maximum drawdown. AVGO's return was also substantial, but its -41.15% drawdown illustrates that a strong overall return does not eliminate substantial interim losses. INTC's -70.80% maximum drawdown was the deepest of the six. Consequently, selecting a stock on cumulative return alone would omit important historical risk information.

## Impact and decision quality

The practical contribution is a repeatable way for a hypothetical analyst to view returns and downside experience together, switch between securities, and examine a selected date range. This may make historical comparison easier to communicate; **we have not measured stakeholder adoption, time saved, financial benefit, or real-world investment outcomes**. The relevant decision rule is to present return, volatility, and drawdown together rather than claim that the highest-return security is automatically the best choice.

## Validation and acceptance

The team coordinator reported and logged **36 Power BI KPI comparisons passing to two displayed decimal places**: 18 for the full 2021–2025 window and 18 for the 2024-only window (six securities × three KPIs for each window). Full-period values were compared against the processed KPI CSV. The 2024 returns were checked against saved notebook results, while 2024 volatility and window-reset maximum drawdown were independently calculated from uploaded daily data. The dated [validation record](week08_validation_record.md) includes actual values, expected values, methods and limitations.

On October 12, Luis reported restarting the Jupyter kernel and successfully running the master notebook top-to-bottom, then uploading the executed file. Direct inspection of the uploaded GitHub notebook confirmed **16 of 16 code cells with execution counts and no saved error outputs**. This supports successful execution in Luis's environment, **not yet independent clean-environment reproducibility**. Rey's independent notebook test and Colen's independent PBIX review have been requested and remain pending.

Acceptance is limited to the tested data snapshot, methods, display precision and interactions. Passing checks does not independently certify market-data provenance, every dashboard interaction, or behavior on a different machine.

## Limitations and unknowns

1. **Historical scope:** January 2021–December 2025; results are descriptive and cannot predict future performance.
2. **Selection and benchmark:** Five selected semiconductor stocks do not represent the entire sector. SPY is a broad U.S. equity benchmark, not a semiconductor-sector control.
3. **Price methodology:** Adjusted prices and a specific saved data snapshot determine calculated results. A later live yfinance download may differ. Volatility annualizes daily return variation using a 252-trading-day convention; maximum drawdown depends on the selected window's running peak.
4. **Risk coverage:** Volatility and maximum drawdown do not capture every relevant investment risk, transaction cost, tax consequence, or investor constraint.
5. **Validation boundary:** Dashboard readings were reported by Luis, not independently inspected by another team member. Independent teammate review, signed-out accessibility checks, environment capture and demo replay are not yet complete.
6. **Impact boundary:** The stakeholder is hypothetical; no deployment, measured business improvement, predictive accuracy, or investment performance is claimed.

See the [impact and risk register](week08_impact_risk_register.md) for risks, owners and mitigations.

## Demo plan and accessible alternative

The planned demonstration introduces the research question, traces the saved data through the Jupyter notebook to the KPI CSV, opens the Power BI dashboard, compares securities, changes the 2024 date filter, and interprets the three measures together. It ends with limitations and the validation boundary. The [text demo outline and readiness checklist](week08_demo_outline.md) provide a readable alternative to a visual walkthrough. A captioned backup recording or equivalent accessible walkthrough **has not yet been confirmed**.

Before submission, the team must freeze an exact reviewed commit or tag; confirm the authorized sample input, dependencies and environment; verify links while signed out; inspect for credentials or restricted information; prepare demo backup; and obtain individual reviews from Luis, Rey and Colen. The [work plan and contribution record](week08_work_plan_contribution_record.md) identifies owners, dependencies, acceptance criteria and current evidence. Requests to Rey and Colen are **not** represented as completed work.

## Sources and verification

- [Project README](../README.md): scope, dataset, methods, project research questions and reported full-period KPIs.
- [Executed Jupyter notebook](../notebooks/CIS480_Final_Master_Analysis.ipynb) and [saved Week 7 notebook](../notebooks/CIS480_Final_Master_Analysis_W07.ipynb): computation and calendar-year sensitivity evidence.
- [Processed KPI CSV](../data/processed/kpi_summary_metrics_2021_2025.csv) and [cleaned market data CSV](../data/processed/cleaned_market_data_2021_2025.csv): data and numerical evidence.
- [Week 8 validation record](week08_validation_record.md): dated test methods, reported outputs and acceptance decisions.
- [yfinance project](https://github.com/ranaroussi/yfinance): historical market-data retrieval library; prices were not independently verified against an exchange or vendor in Week 8.

## AI-use disclosure

ChatGPT assisted Luis with drafting and organizing this Section 6 report, structuring the Week 8 validation and contribution records, comparing reported Power BI values with saved notebook/CSV calculations, and writing draft team coordination messages. Luis performed the reported Power BI checks and Jupyter execution, reviewed the resulting outputs, and uploaded the executed notebook. The numerical statements in this report were cross-checked against the project's saved evidence and dated validation record; they should be reviewed again by the team before submission. AI assistance does **not** substitute for teammates' independent testing, first-hand review, or the team's responsibility for accuracy. Material revisions before submission should be reflected in GitHub commits and the contribution record.

## Finalization status

**Not yet approved for submission.** Outstanding: Rey's independent reproducibility evidence, Colen's independent dashboard evidence, teammate review confirmations, demo freeze and backup, public-link and security checks, and final accessibility review.

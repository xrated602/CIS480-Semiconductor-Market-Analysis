# Week 8 — Impact and Risk Register

| ID | Impact / risk | Evidence or rationale | Likelihood | Consequence | Mitigation / decision rule | Proposed owner | Status |
|---|---|---|---|---|---|---|---|
| R1 | Historical results mistaken for investment predictions | Five-year descriptive market comparison | Medium | High | Explicitly label historical only; no forecasts or recommendations | Luis | Open |
| R2 | High cumulative returns obscure volatility and drawdown | NVDA 1326.20% return, 52.22% volatility, -66.34% max drawdown (README rounded values) | Medium | High | Show return and both risk measures together | Luis | Open |
| R3 | Broad-market benchmark interpreted as sector-matched control | SPY tracks broad US market, not semiconductor sector | Medium | Medium | State benchmark limitations on report/dashboard | Colen | Open |
| R4 | Data revisions alter reproducibility | yfinance downloads can change after notebook execution | Medium | High | Use committed authorized snapshot, fixed commit and recorded library versions | Rey | Open |
| R5 | Dashboard interactions differ from notebook KPIs | PBIX not independently tested for Week 8 | Unknown | High | Inspect slicers and KPI values against frozen CSV; log actual outputs | Luis | Open |
| R6 | Live demo fails or links require sign-in | External runtime/Power BI dependencies | Medium | Medium | Prepare offline copy, backup recording, text outline and signed-out link test | Luis | Open |
| R7 | Contribution claims lack traceable evidence | Team review required for every member | Medium | High | Require direct artifact or material revision link and member sign-off | All | Open |

**Impact interpretation:** The dashboard helps a hypothetical analyst compare historical risk and performance using consistent measures. No real stakeholder adoption, investment outcome, or predictive accuracy is claimed.

## R5 update — 2026-10-15 independent review

Colen's independent PBIX review found that ticker slicer selection does not consistently update KPI cards and that conflicting chart selections can blank the cards. **R5 is now a confirmed, open interaction defect (not merely an untested possibility).** Proposed response: reproduce the selections; inspect slicer-to-card interactions, measures and cross-filter settings; correct or explicitly document intended behavior; retest against the committed KPI CSV; preserve before/after evidence. Do not call the dashboard fully accepted until this is resolved or disclosed with its impact.

### R5 design clarification — 2026-10-16

Luis explained that the Security slicer intentionally filters **only KPI cards**, while the Date slicer filters **KPI cards and charts**. The absence of Security-slicer filtering on charts is therefore **by design**, not a defect. The remaining risk is whether chart clicks unexpectedly blank KPI cards or prevent a selected security's metrics from displaying; test and document this separately before closing R5. Prior R5 wording treating all ticker/card interaction observations as a confirmed defect is superseded by this clarification.

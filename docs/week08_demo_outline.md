# Week 8 — Demo Day Outline and Readiness Checklist

## Presentation outline (text alternative)
1. **Problem and audience:** Hypothetical analyst needs comparable historical risk/performance across AMD, AVGO, INTC, NVDA and TSM relative to SPY.
2. **Data and pipeline:** Authorized 2021–2025 daily adjusted prices; frozen CSV -> Python/Jupyter validation and KPIs -> Power BI.
3. **Inspect source and calculation:** Open the frozen notebook and processed KPI CSV. Demonstrate SPY cumulative-return baseline and NVDA volatility reconciliation, distinguishing prior tests from Week 8 reruns.
4. **Dashboard demonstration:** Show cumulative return, annualized volatility and maximum drawdown; select a security and adjust date filters. Explain that changing date ranges may require KPI recomputation depending on dashboard implementation.
5. **Interpretation:** NVDA and AVGO have the largest historical cumulative returns in the documented table, while every semiconductor security has higher volatility and deeper maximum drawdown than SPY.
6. **Limitations:** Historical window, adjusted-price choices, benchmark mismatch, missing investment-risk dimensions, hypothetical stakeholder.
7. **Questions and backup:** Use an accessible recorded walkthrough and this text outline if the live demo fails.

## Readiness checklist
- [ ] Freeze and link an exact reviewed commit SHA or demo tag.
- [ ] Confirm authorized sample input is downloadable.
- [ ] Record Python/library environment and execution instructions.
- [ ] Run notebook top to bottom from frozen input and record date/results.
- [ ] Open PBIX and compare dashboard values with frozen outputs.
- [ ] Capture accessible backup recording with captions/transcript or provide equivalent text explanation.
- [ ] Check all links while signed out; document the result.
- [ ] Inspect repository and demo materials for credentials, private paths, student information and restricted content.
- [ ] Obtain Luis, Rey and Colen's separate review comments.

**Current status:** Outline prepared; no live demo, backup recording, freeze or signed-out verification is claimed.

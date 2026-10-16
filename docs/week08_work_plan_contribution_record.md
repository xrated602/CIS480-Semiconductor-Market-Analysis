# Week 8 — Work Plan and Contribution Record

**Due:** October 18, 2026, 11:59 p.m. Arizona time.

The owner assignments below follow documented project responsibilities. **They are proposed Week 8 tasks, not proof of completion or individual contributions.** Replace pending entries with links to actual commits, files, or signed review comments.

| Owner | Task | Status | Dependency | Acceptance criterion | Contribution evidence |
|---|---|---|---|---|---|
| Luis Ramirez | Finalize Section 6 interpretation and demo narrative | In progress | Reviewed KPI output | Claims match frozen evidence; uncertainty and decision limits explicit | Add report commit/link |
| Luis Ramirez | Verify Power BI visuals and demo accessibility | Pending | Frozen processed CSV and PBIX | All six securities, three KPIs, date and security filters inspected | Add dated test evidence |
| Rey Guirette | Confirm data provenance, frozen sample and cleaning checks | Pending | Dataset snapshot | Public/authorized data; dates, tickers and quality checks reconciled | Add review comment and relevant file/commit |
| Colen Wilson | Review calculations and independent validation | Pending | Frozen notebook and KPI CSV | SPY return and NVDA volatility reconciled; interpretation accurate | Add test output and review comment |
| Luis Ramirez | Integrate demo tag/commit, backup and public-link check | Pending | Tests and teammate reviews | Commit SHA fixed, signed-out links checked, fallback available | Add tag/commit, recording/text outline |
| Entire team | Review final package | Pending | Final files and links | Each member confirms scope, evidence, limitations and own contribution | Individual GitHub review comments |

## Decisions and dependencies
- Benchmark is **SPY**, not Nasdaq-100, per project README.
- Analyze **AMD, AVGO, INTC, NVDA, TSM** against SPY over **2021–2025**.
- Do not freeze a demo tag before final files and tests are reviewed.
- Do not mark reviews complete on behalf of teammates without their confirmation.

## Assignment coordination update — 2026-10-12

Luis reported emailing Rey and Colen their separate Week 8 assignments. These are requests for review, **not completed teammate contributions**.

- **Luis:** Completed user-reported Power BI visual testing (36 full-period and 2024 KPI comparisons), fresh local Jupyter master-notebook execution, uploaded executed notebook, and coordinated the independent review requests. Continue Section 6 integration, final demo evidence, link/security checks and submission.
- **Rey:** Requested to independently restart and run the master Python notebook, check data loading, methodology, dependencies, README/setup, repository structure, Week 8 documentation, and Python demo explanation. Requested a result summary and screenshot if possible by October 16. **Awaiting confirmation and evidence.**
- **Colen:** Requested to independently open/test the PBIX dashboard, verify all six tickers, slicers, KPI behavior and usability, review Week 8 documentation and findings, and prepare Power BI demo explanation. Requested a result summary and screenshot if possible by October 16. **Awaiting confirmation and evidence.**
- **All:** Final review and demo rehearsal remain pending. Do not attribute a completed review to Rey or Colen until their actual feedback is received.

The original planning table above reflects earlier proposed assignments; this dated update records the latest requests.

## Verified coordination update — 2026-10-13 (supersedes Rey's pending status above)

**Rey Guirette — COMPLETE for his assigned independent notebook, methodology, repository and Week 8 documentation review.** Rey emailed Luis a three-page PDF, *Reys Week 8 Tasks.pdf*, dated October 13. He reports successful independent runs of `CIS480_Final_Master_Analysis.ipynb` in Google Colab and Anaconda Jupyter with no errors or missing dependencies, successful file exports, and sufficient README/setup instructions. He reviewed the 2021–2025 adjusted-price method and AMD, AVGO, INTC, NVDA, TSM versus SPY scope, and reviewed the Week 8 validation, work-plan, impact-risk and demo-outline documents. He confirmed the demo outline and recommended no changes. [Rey's detailed evidence summary](week08_rey_independent_review_2026-10-13.md).

**Contribution effect:** A dated teammate-run reproducibility smoke test in two environments and independent documentation review. **Evidence limit:** Rey's PDF shows screenshots of exported files, not full cell execution logs or a numerical recheck of every KPI. The original PDF remains with Luis and must be uploaded or attached to the final package for direct inspection. Rey's final review of the *complete submission package* is still pending, as are Colen's independent review and the team's final sign-offs. The original planning row and October 12 note are historical; use this October 13 update as Rey's current status.

## Independent dashboard review received — 2026-10-15

**Colen Wilson — ASSIGNED REVIEW COMPLETE; remediation and retest OPEN.** Colen supplied *Colens Week 8 Tasks.pdf* (five pages) documenting independent dashboard tests, usability review, Week 8 documentation review, findings and Power BI demo explanation. He confirmed successful PBIX opening, all six securities, date slicer, labels and findings. He found **ticker slicer/KPI card interaction problems** and chart-selection conflicts that can blank KPI values. He recommended clarifying the cumulative-return card title, prioritizing the ticker slicer layout and increasing line-chart height. His documentation review required no corrections. **Contribution effect:** Independent detection of a material dashboard interaction defect and a documented usability/interpretation review. **Evidence:** Colen's original PDF supplied to Luis, pending GitHub/Canvas upload; [PBIX](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) and [dated validation entry](week08_validation_record.md). **Acceptance status:** Independent review delivered, **not** full PBIX functional acceptance; correction and retest are required or the unresolved behavior must be explicitly disclosed. Rey's October 13 independent notebook review is also complete. Final three-member signoff and demo backup remain pending.

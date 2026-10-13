# CIS480 Week 8 — Team Submission Package

**Project:** Historical Market Performance and Risk Analysis of Semiconductor Stocks  
**Team:** Luis Ramirez, Rey Guirette, Colen Wilson  
**Due:** Sunday, October 18, 2026, 11:59 p.m. Arizona time  
**Status:** In progress — **do not submit until final review and accessibility checks are complete.**

## Start here

This page is the entry point for the **T08 Section 6 Solution Interpretation** team submission and supporting evidence. It also provides reusable project evidence for the M08 Demo Day milestone. Our historical analysis compares **AMD, AVGO, INTC, NVDA and TSM** with the **SPY** broad-market benchmark over **2021–2025**.

The project is descriptive, not a prediction or investment recommendation.

## Required report and project artifacts

| Requirement | Inspectable evidence | Current status |
|---|---|---|
| Complete Section 6 interpretation, impact, reasoning, limitations | [Section 6 working report](week08_section6_solution_interpretation.md) | Draft complete; team approval pending |
| Executed analytical artifact | [Final master Jupyter notebook](../notebooks/CIS480_Final_Master_Analysis.ipynb) | Executed and uploaded by Luis; independent rerun pending |
| Authorized historical input | [Cleaned market data CSV](../data/processed/cleaned_market_data_2021_2025.csv) | Committed; independent source/access review pending |
| Expected and actual KPI outputs | [Processed KPI summary CSV](../data/processed/kpi_summary_metrics_2021_2025.csv) | Available |
| Working interactive MVP | [Power BI dashboard file](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) | Available; independent PBIX review pending |
| Dated acceptance tests with inputs, expected/actual results, status and evidence | [Week 8 validation record](week08_validation_record.md) | 36 Luis-reported dashboard comparisons passed; additional checks pending |
| Impact and governance risks | [Impact-risk register](week08_impact_risk_register.md) | Draft complete; final updates pending |
| Owner, task, status, dependency, acceptance criteria and contribution evidence | [Work plan and contribution record](week08_work_plan_contribution_record.md) | Updated; teammate evidence pending |
| Accessible text alternative to demonstration | [Demo outline and readiness checklist](week08_demo_outline.md) | Available |
| Setup instructions and dependencies | [Project README](../README.md) and [requirements.txt](../requirements.txt) | Available; Rey's independent environment check pending |
| Presentation and backup recording | [M08 team PowerPoint presentation](CIS480_M08_Demo_Day_Team_Presentation.pptx) uploaded to `docs/`; accessible backup recording/transcript to be added | Presentation uploaded and repository file verified; backup recording pending |
| Frozen demo version | Reviewed commit SHA or tag to be linked here | Pending |
| Signed-out links, secrets scan and accessibility inspection | Dated final verification results to be added to [validation record](week08_validation_record.md) | Pending |
| Each member's final approval and contribution evidence | [Work plan and contribution record](week08_work_plan_contribution_record.md) and signed GitHub review comments | Pending |

## Validation summary and boundaries

Luis reported 18 full-period and 18 calendar-year-2024 KPI comparisons across six securities and three measures, all agreeing to **two displayed decimal places** with saved project evidence. On October 12, Luis reported a successful local restart-and-run-all of the master notebook, uploaded the executed notebook, and its 16 executed code cells were inspected without saved error outputs. See the [validation record](week08_validation_record.md) for methods and results.

These observations do **not** prove that another machine can reproduce the analysis, that every Power BI interaction works, or that underlying market prices were independently certified. Rey was asked to rerun and review Python; Colen was asked to inspect Power BI and the project findings. Neither review is marked complete without actual results.

## What the results support

The saved full-period KPI table shows NVDA and AVGO with the largest cumulative returns, while all five semiconductor securities have higher volatility and deeper maximum drawdowns than SPY. The dashboard enables comparison of historical return and risk for a hypothetical analyst. No measured real-world stakeholder adoption, financial benefit, forecast accuracy, or future investment performance is claimed.

See [Section 6](week08_section6_solution_interpretation.md) for exact metrics, decision implications, and limitations.

## Demonstration and handoff

1. State the stakeholder need and project question.
2. Show the committed data input and executed notebook.
3. Explain cumulative return, annualized volatility, maximum drawdown and the acceptance criteria.
4. Open the Power BI dashboard and demonstrate ticker/date selection.
5. Interpret the return-versus-risk tradeoffs and benchmark limitations.
6. Show the dated validation evidence, limitations and risk mitigations.
7. Identify the next handoff: independently reviewed, reproducible and accessible final package.

[Readable demonstration outline](week08_demo_outline.md) and [M08 team PowerPoint presentation](CIS480_M08_Demo_Day_Team_Presentation.pptx). The PowerPoint file has been verified in the repository, but the team must still provide an accessible backup recording or approved equivalent with captions or a text alternative **before claiming demo readiness**.

## Final submission checklist

- [ ] Rey's independent notebook execution, environment/setup observations and evidence recorded.
- [ ] Colen's independent Power BI and documentation review recorded.
- [ ] Luis, Rey and Colen each reviewed the complete final package and confirmed their contributions.
- [ ] Exact approved demo commit SHA or tag recorded here.
- [ ] Authorized input, expected and actual outputs, and dependency versions verified.
- [ ] Presentation [uploaded](CIS480_M08_Demo_Day_Team_Presentation.pptx); signed-out access and accessible backup recording or approved equivalent still to be verified.
- [ ] Every public evidence link opened and verified while signed out.
- [ ] Credentials, private contacts, restricted information and personal data checked.
- [ ] Sources, AI assistance, verification and material revisions disclosed.
- [ ] Final Section 6 and contribution records updated to reflect completed (not merely assigned) work.
- [ ] One team member submits this package URL or approved file in Canvas by the deadline.

## Sources, AI use and integrity

The [Section 6 report](week08_section6_solution_interpretation.md) includes project sources, verification boundaries and the ChatGPT AI-use disclosure. This landing page was drafted with ChatGPT to organize existing GitHub evidence and rubric requirements. It does not certify that outstanding tests or checks occurred. Team members must review, revise, and verify its claims and links before submitting.

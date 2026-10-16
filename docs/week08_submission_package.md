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
| Complete Section 6 interpretation, impact, reasoning, limitations | [Section 6 working report](week08_section6_solution_interpretation.md) | Draft complete; Rey and Colen reviewed final package per Luis; Luis final submission confirmation pending |
| Executed analytical artifact | [Final master Jupyter notebook](../notebooks/CIS480_Final_Master_Analysis.ipynb) | Executed and uploaded by Luis; Rey reports successful independent reruns |
| Authorized historical input | [Cleaned market data CSV](../data/processed/cleaned_market_data_2021_2025.csv) | Committed; independent source/access review pending |
| Expected and actual KPI outputs | [Processed KPI summary CSV](../data/processed/kpi_summary_metrics_2021_2025.csv) | Available |
| Working interactive MVP | [Power BI dashboard file](../powerbi/CIS480_Semiconductor_Market_Performance_Dashboard.pbix) | Corrected PBIX uploaded; Colen reviewed original and Luis verified corrected interactions |
| Dated acceptance tests with inputs, expected/actual results, status and evidence | [Week 8 validation record](week08_validation_record.md) | 36 Luis-reported KPI comparisons and three downloaded-PBIX interaction tests passed |
| Impact and governance risks | [Impact-risk register](week08_impact_risk_register.md) | Draft complete; final updates pending |
| Owner, task, status, dependency, acceptance criteria and contribution evidence | [Work plan and contribution record](week08_work_plan_contribution_record.md) | Updated; Rey and Colen final-package reviews confirmed by Luis |
| Accessible text alternative to demonstration | [Demo outline and readiness checklist](week08_demo_outline.md) | Available |
| Setup instructions and dependencies | [Project README](../README.md) and [requirements.txt](../requirements.txt) | Available; Rey reports independent Colab and Anaconda runs passed |
| Presentation and backup recording | [M08 team PowerPoint presentation](CIS480_M08_Demo_Day_Team_Presentation.pptx) uploaded to `docs/`; accessible backup recording/transcript to be added | Presentation uploaded and repository file verified; recording/equivalent requirement to be confirmed |
| Frozen demo version | Reviewed commit SHA or tag to be linked here | Pending |
| Signed-out links, secrets scan and accessibility inspection | Dated final verification results to be added to [validation record](week08_validation_record.md) | Pending |
| Each member's final approval and contribution evidence | [Work plan and contribution record](week08_work_plan_contribution_record.md) and signed GitHub review comments | Pending |

## Validation summary and boundaries

Luis reported 18 full-period and 18 calendar-year-2024 KPI comparisons across six securities and three measures, all agreeing to **two displayed decimal places** with saved project evidence. On October 12, Luis reported a successful local restart-and-run-all of the master notebook, uploaded the executed notebook, and its 16 executed code cells were inspected without saved error outputs. See the [validation record](week08_validation_record.md) for methods and results.

These observations do **not** prove that another machine can reproduce the analysis, that every Power BI interaction works, or that underlying market prices were independently certified. Rey's independent notebook review and Colen's initial dashboard review are documented; Luis subsequently remediated Colen's interaction finding and passed three regression tests on the downloaded GitHub PBIX. Colen did not retest the revision.

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

[Readable demonstration outline](week08_demo_outline.md) and [M08 team PowerPoint presentation](CIS480_M08_Demo_Day_Team_Presentation.pptx). The PowerPoint file has been verified in the repository. The readable outline is available as a text alternative. Confirm the course's backup-recording/equivalent requirement separately; the team plans to submit the demo package URL, not claim a recording exists.

## Final submission checklist

- [x] Rey's independent notebook execution, environment/setup observations and evidence summarized in GitHub (original PDF not yet attached).
- [x] Colen's independent Power BI review reported; Luis addressed the interaction issue and passed three downloaded-PBIX regression tests. Colen's second review was intentionally not requested.
- [x] Luis confirms Rey and Colen reviewed the final Week 8 package; Luis is coordinating final verification and submission. Individual written signoffs have not been independently verified.
- [ ] Exact approved demo commit SHA or tag recorded here.
- [ ] Authorized input, expected and actual outputs, and dependency versions verified.
- [ ] Presentation [uploaded](CIS480_M08_Demo_Day_Team_Presentation.pptx); signed-out access and any course-required backup recording/equivalent still to be verified.
- [ ] Every public evidence link opened and verified while signed out.
- [ ] Credentials, private contacts, restricted information and personal data checked.
- [ ] Sources, AI assistance, verification and material revisions disclosed.
- [ ] Final Section 6 and contribution records updated to reflect completed (not merely assigned) work.
- [ ] One team member submits this package URL or approved file in Canvas by the deadline.

## Sources, AI use and integrity

The [Section 6 report](week08_section6_solution_interpretation.md) includes project sources, verification boundaries and the ChatGPT AI-use disclosure. This landing page was drafted with ChatGPT to organize existing GitHub evidence and rubric requirements. It does not certify that outstanding tests or checks occurred. Team members must review, revise, and verify its claims and links before submitting.

## Team evidence update — October 13, 2026

**Rey's assigned Week 8 independent notebook and documentation review: COMPLETE, supported by his emailed PDF.** He reports successful master-notebook runs in Google Colab and Anaconda Jupyter, no missing dependencies or runtime errors, successful file exports, sufficient setup instructions, and review of methodology, Week 8 records and demo outline with no corrections. [Read the dated contribution and test summary](week08_rey_independent_review_2026-10-13.md). This supersedes the earlier *Rey review pending* statements above.

**Evidence still needed:** The original three-page PDF with screenshots is held by Luis and has **not** been uploaded here; attach it to this package or Canvas after checking for private data. Colen's independent PBIX review, each member's final approval of the *complete* package, frozen demo commit/tag, accessible backup, and remaining signed-out/security checks are **not** established by Rey's review. Do not mark the overall team submission ready yet.

**AI-use revision:** ChatGPT structured Rey's emailed review into the linked summary and these status updates on October 13; claims remain attributed to Rey rather than presented as tests performed by ChatGPT.

## Final dashboard validation update — October 16, 2026

Colen completed his independent dashboard review and identified unexpected chart interactions. Luis revised the Power BI visual interactions, uploaded the corrected PBIX to the same GitHub path, downloaded that version, and tested clicking NVIDIA separately in Cumulative Return, Annualized Volatility, and Maximum Drawdown while the Security slicer remained on AMD. All three tests **PASS**: the KPI cards remain on AMD and the other comparison charts retain all six securities. See [dated validation evidence](week08_validation_record.md). Luis elected to close this finding without requesting Colen's second review; **do not imply Colen retested or signed off on the revision**.

The planned submission is this GitHub demo-package URL. The presentation and text outline are linked; whether the course requires an additional backup recording/equivalent remains a separate requirement to verify against the assignment instructions. Remaining work includes final team approval, freeze/tag, complete signed-out checks, and submission.

## Final-package team review confirmation — October 16, 2026

Luis confirms that **Rey Guirette and Colen Wilson have both reviewed the final Week 8 submission package**. This is a team-lead-reported completion of package review, not independently inspected written signoff or a second technical retest by Colen. The corrected PBIX interaction checks were performed by Luis and are documented in the validation record. Final signed-out link checks, frozen commit/tag, and Canvas submission remain outstanding.

## Public-access verification update — October 16, 2026

Luis confirmed in Chrome Incognito, while signed out of GitHub, successful access to 13 linked resources: the submission landing page, master Jupyter notebook, corrected PBIX download, M08 PowerPoint download, Section 6 report, validation record, impact-risk register, work plan/contribution record, demo outline, cleaned market CSV, KPI summary CSV, project README, and `requirements.txt`. Each user-reported result is recorded individually in [the validation log](week08_validation_record.md), W08-17 through W08-29. **Public access PASS for these 13 links.** This does not constitute a secrets/privacy scan or final accessibility audit. Freeze/tag and Canvas submission remain pending.

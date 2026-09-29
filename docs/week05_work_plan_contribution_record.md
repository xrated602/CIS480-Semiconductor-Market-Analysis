# Week 5 Work Plan and Contribution Record

## Project
**Historical Market Performance and Risk Analysis of Selected Semiconductor Stocks**

**Team:** Luis Ramirez, Rey Guirette, Colen Wilson

This record documents the current Week 5 work plan, ownership, dependencies, acceptance criteria, and contribution evidence for the team project.

## Current Work Plan

| Owner | Task | Status | Dependency | Acceptance Criterion | Contribution Evidence |
|---|---|---|---|---|---|
| Rey Guirette | Historical data retrieval, preparation, data-quality support, and original data dictionary | Complete / integrated | Required market data and agreed project tickers/date range | Required source fields are available for all six securities and documentation describes the analytical fields | Rey's individual branch; original data dictionary; final team-reviewed dictionary in `docs/data_dictionary.txt` |
| Colen Wilson | Review Python calculations and provide independent KPI/analysis validation | Complete / integrated | Cleaned analytical data and agreed KPI definitions | Calculations can be reviewed against the master analysis and discrepancies are resolved before final use | Colen's individual branch and analysis/validation notebook |
| Luis Ramirez | Project coordination, research questions/KPIs, master-notebook integration, Power BI dashboard, repository organization, and Week 5 documentation | Complete / integrated | Rey and Colen's individual work plus final integrated dataset | Master workflow runs end-to-end, Week 5 data-quality checks pass, dashboard uses validated outputs, and required documentation is traceable in the repository | `notebooks/CIS480_Final_Master_Analysis.ipynb`, Power BI artifact, README, `docs/data_card.md`, `docs/week05_validation_record.md`, and repository integration commits |
| Team | Review final Week 5 package | Complete | Data dictionary, data card, validation record, limitations, sources/AI disclosure, and contribution evidence completed | All required Week 5 components are present, accessible, consistent with the executed notebook, and reviewed before submission | Final files and commit history on `main` |

## Contribution Details

### Rey Guirette
Rey's work contributed to the data preparation and documentation side of the project. His original data dictionary documented the core analytical fields and their formulas. During Week 5 integration, the team reviewed that dictionary against the final master dataset and expanded it to match the final 15-field structure and executed validation results.

**Material effect on project:** Rey's work helped establish the dataset structure and documentation needed to trace the analytical fields back to the preprocessing workflow.

**Evidence:** `rey-work` branch and `docs/data_dictionary.txt`.

### Colen Wilson
Colen reviewed the KPI calculations and created analysis/validation work that could be compared with the integrated project calculations.

**Material effect on project:** His work provided a separate review point for the team's calculations rather than relying only on the integrated master notebook.

**Evidence:** `colen-work` branch and Colen's analysis/validation notebook.

### Luis Ramirez
Luis coordinated the integrated project, defined and maintained the research-question/KPI direction, combined team work into the master analysis, developed the Power BI dashboard, organized the GitHub repository, and integrated the Week 5 data-quality documentation.

For Week 5, Luis added the data-quality profile and validation section to the master notebook. The executed checks confirmed 7,530 rows, 1,255 trading dates, six required securities, zero duplicate `Trading_Date + Ticker` keys, zero missing adjusted closing prices, and the expected structural missing values for return-dependent fields.

**Material effect on project:** This work connected the team's data preparation and calculations to an inspectable final workflow and documented whether the final analytical dataset met the Week 5 acceptance rules before use in Power BI.

**Evidence:** `notebooks/CIS480_Final_Master_Analysis.ipynb`, Power BI artifact, README, `docs/data_card.md`, `docs/week05_validation_record.md`, and GitHub commit history.

## Current Dependencies
The core analytical workflow and Week 5 validation are complete. The Section 3 narrative, limitations statement, sources/AI-use disclosure, and required Week 5 evidence have been assembled and reviewed for final submission.

A separate data-governance issue remains documented in the data card: the project has not established unrestricted redistribution rights for the underlying Yahoo Finance market data. This does not change the internal Week 5 validation result, but it affects how raw source-derived data should be shared.

## Team Acceptance Criteria
The Week 5 package is ready for submission when:
1. The final master notebook runs end-to-end and retains the executed Week 5 validation evidence.
2. The data dictionary matches the final analytical dataset.
3. The data card documents provenance, use, preprocessing, missingness, limitations, and permission risk.
4. The validation record reports expected and actual results and the decision rule.
5. Each team member is linked to specific contribution evidence.
6. The Section 3 narrative distinguishes supported evidence from limitations or unknowns.
7. Sources and AI use are disclosed.
8. The final package is reviewed for accessibility and consistency before submission.

## Current Status
**Week 5 technical evidence: Complete.**  
**Week 5 documentation package: Complete.**  
**Final team review: Complete.**  
**Submission status: Ready for submission.**

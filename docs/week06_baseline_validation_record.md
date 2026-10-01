# Week 6 Baseline Validation Record

## Test purpose
Verify one meaningful calculation in the smallest complete analytical pipeline path by independently reconciling SPY cumulative return with the project's pipeline result.

| Field | Record |
|---|---|
| Test | SPY cumulative-return reconciliation |
| Evaluation unit | SPY over the complete project observation period |
| Input | Beginning adjusted close = 341.588684; ending adjusted close = 676.635010 |
| Baseline formula | `(Ending Adjusted Close / Beginning Adjusted Close) - 1` |
| Expected result | Independent baseline agrees with the pipeline result within 0.01 percentage point after rounding |
| Independent baseline result | 0.98084726 = 98.0847% |
| Existing displayed pipeline result | 98.08% |
| Difference from displayed two-decimal result | 0.0047 percentage point |
| Decision rule | PASS when the notebook's unrounded pipeline result differs from the independent baseline by no more than 0.0001 as a proportion (0.01 percentage point) |
| Status | PASS for the displayed reconciliation; the notebook assertion provides the reproducible unrounded test when executed |
| Evidence | `notebooks/CIS480_Final_Master_Analysis.ipynb`, Week 6 section |

## Interpretation
The independent calculation produces approximately **98.0847%**, which reconciles with the existing displayed KPI of **98.08%** after rounding.

## Evidence boundary and limitations
This reconciliation supports the specific SPY cumulative-return calculation. It does not prove every source value, every KPI, or every Power BI interaction is error-free, and historical performance does not predict future performance. Random cross-validation is not appropriate because this is a descriptive dashboard project rather than a predictive model.

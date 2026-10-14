# Rey Guirette — Week 8 Independent Review Evidence

**Reviewer:** Rey Guirette  
**Review date:** October 13, 2026  
**Source:** Three-page PDF provided by Rey to Luis by email, titled *Reys Week 8 Tasks.pdf*, and accompanying email summary.  
**Evidence type:** Faithful text summary of teammate-provided review; **the original PDF and its screenshots are not stored in this repository by this entry**.

## Independent Python notebook execution

**Input / question:** Does `notebooks/CIS480_Final_Master_Analysis.ipynb` execute in separate environments, load data, and export analysis files without missing dependencies?

**Expected:** Successful notebook execution and data exports, no reported runtime errors or missing dependencies.

**Actual reported by Rey:** **PASS**, independently run on **Google Colab** and **Anaconda Jupyter Notebook** on October 13, 2026. Rey reports no errors or missing dependencies. He cites the notebook's final message, “Final project files exported successfully,” and says the data loads and outputs follow the expected extract, calculate, transform, and export sequence. Page 1 of his PDF includes screenshots of the generated raw, cleaned, formatted and KPI-summary CSV files in both environments.

**Status:** PASS — **Rey-reported independent environment execution**; PDF screenshots show output files, not a full captured cell-by-cell execution log.

## Data and methodology review

Rey reports confirming the 2021–2025 historical window, AMD/AVGO/INTC/NVDA/TSM against SPY, consistent adjusted closing prices, explained cumulative return / annualized volatility / maximum drawdown calculations, and historical descriptive rather than predictive framing. He references notebook block 12 for validation.

**Status:** Reviewed, no issue reported. This is a methodology review, not a separate independent recomputation of every KPI.

## Repository and documentation review

Rey reports the README, notebook setup instructions, dependencies, folder structure, and links to notebook, dashboard and documentation were sufficient and working. He initially found the coexistence of the Week 7 and master notebook files slightly confusing but understood the file-type organization; he recommends no changes.

He also reviewed the Week 8 validation record, work-plan/contribution record, impact-risk register and demo outline, reporting no corrections needed. His accompanying email explicitly confirms demo-outline review.

**Status:** Reviewed by Rey; no recommendations made.

## Contribution and limitations

**Specific contribution:** Independent two-environment notebook smoke test, methodology review, repository/setup and documentation review, and demo-outline review. **Effect:** Adds a dated teammate confirmation of reproducibility in two reported environments and a review of the demo's analytical narrative.

**Evidence boundaries:** Rey's report does not independently demonstrate all historical source-price values, every KPI's numerical equality with the frozen CSV, every Power BI slicer/visual, a signed-out-browser access test, an offline frozen-input run, or final approval of the *complete* team package. It also does not identify a GitHub commit authored by Rey. Keep those checks separate.

**Original source:** *Reys Week 8 Tasks.pdf*, pages 1–3, received from Rey by email on October 13, 2026. **Action still needed:** upload the original PDF with its screenshots to this repository or attach it to the Canvas team package, after checking for private information.

**AI-use note:** ChatGPT assisted in converting the teammate-provided email/PDF into this structured evidence summary. The summary preserves Rey's reported findings and distinguishes reported observations from independently inspected tests. Team members should verify this transcription against the original PDF.

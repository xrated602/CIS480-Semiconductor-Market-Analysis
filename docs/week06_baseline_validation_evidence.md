### **SPY Cumulative-Return Baseline Validation Evidence**

The master notebook was reviewed to validate the SPY cumulative-return calculation and its underlying inputs.

**1\. SPY input validation**

The notebook confirms that SPY was included in the requested security set and that the downloaded data passed the initial input validation. The data covered January 4, 2021 through December 31, 2025, with no duplicate dates and no missing Close values for SPY.

**2\. Cumulative-return formula**

The notebook's first-build calculation defines cumulative return as:

`(Last Close / First Close - 1) × 100`

The final ETL independently implements the same calculation in numeric proportion form:

`(Adj_Close / start_price) - 1`

This confirms that the baseline and final pipeline use the same underlying cumulative-return definition.

**3\. SPY input values**

The final KPI summary reports the following SPY values:

* First/Start Price: **341.588684**  
* Last/End Price: **676.635010**  
* Pipeline Cumulative Return: **0.980847**

The first-build validation independently reports the SPY cumulative return as **98.08%** after presentation rounding.

**4\. Independent recalculation**

Using the notebook's reported SPY start and end prices:

`(676.635010 / 341.588684) - 1 = 0.9808472637`

The unrounded independent result is therefore approximately **0.980847264**.

Compared with the pipeline result of **0.980847**, the absolute difference is approximately:

`|0.9808472637 - 0.980847| = 0.000000264`

This difference is substantially smaller than a **0.0001 tolerance**.

**5\. Final validation status**

The notebook's final validation cell independently recalculates cumulative returns from the first and last adjusted-close values and compares those results with the reported KPI values. The assertion passes, and the notebook prints:

**“All final validation checks passed.”**

### **Conclusion**

The notebook evidence supports the conclusion that the SPY cumulative-return calculation is correctly implemented, uses the intended SPY input series, and agrees with an independent first/last-price calculation to substantially better than a 0.0001 tolerance. No material correction to the cumulative-return baseline is indicated by the master notebook.


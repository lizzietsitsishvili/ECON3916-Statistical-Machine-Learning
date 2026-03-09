## Project Overview

This project investigates the risks of spurious correlation and multicollinearity in macroeconomic time-series data using data retrieved from the Federal Reserve Economic Data (FRED) API. Macroeconomic indicators often exhibit strong correlations in their raw levels due to shared time trends rather than meaningful economic relationships. The objective of this analysis was to demonstrate how these statistical traps can mislead interpretation and modeling if not properly addressed.

Using Python, the analysis began with data ingestion and manipulation through pandas, followed by exploratory visualization using seaborn to construct correlation matrices and regression plots. These visualizations revealed strong correlations between several macroeconomic indicators—including inflation, unemployment, industrial production, and money supply—highlighting the potential for misleading relationships in non-stationary time-series data.

To formally diagnose redundancy among predictors, Variance Inflation Factor (VIF) diagnostics were implemented using statsmodels. The VIF results quantified the degree of multicollinearity present in the raw level variables, confirming that many indicators contained overlapping information.

To address these issues, the macroeconomic series were transformed into Year-over-Year (YoY) growth rates, which helps remove deterministic trends and improve stationarity. The transformed dataset significantly reduced artificial correlations and produced relationships that more closely reflect genuine economic dynamics.

Finally, Directed Acyclic Graphs (DAGs) were used to conceptualize the structural relationships among the macroeconomic variables. This framework helps distinguish between correlation and causation by illustrating the hypothesized pathways through which economic forces interact.

Overall, this project demonstrates how careful data transformation, diagnostic testing, and causal reasoning are essential for producing reliable insights from macroeconomic time-series data.

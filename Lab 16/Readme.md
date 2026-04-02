High-Dimensional GDP Growth Forecasting with Lasso and Ridge Regularization
Objective

Develop a predictive model for 5-year average GDP per capita growth across countries, demonstrating the limitations of OLS in high-dimensional settings and applying regularization techniques to improve out-of-sample performance.

Methodology
Collected cross-country macroeconomic data from the World Bank World Development Indicators (WDI) using the wbgapi Python API
Constructed a dataset of 120+ countries with 30+ economic, social, and institutional predictors
Split the data into training and testing sets to evaluate out-of-sample performance
Estimated a baseline OLS regression to illustrate overfitting in a high p/n environment
Standardized predictors to ensure comparability across variables
Implemented Ridge Regression (RidgeCV) with cross-validated lambda selection to reduce coefficient variance
Implemented Lasso Regression (LassoCV) to perform both regularization and feature selection
Visualized the Lasso Path to analyze how predictors enter the model as regularization strength changes
Compared model performance using training vs. test R² to assess generalization
Key Findings
The OLS model exhibited severe overfitting, achieving near-perfect training performance (R² ≈ 1.0) but significantly lower test performance, highlighting variance explosion in high-dimensional settings
Both Ridge and Lasso regularization reduced the train–test performance gap, improving model stability and predictive reliability
Lasso produced a sparse model, selecting a small subset of the most informative predictors (approximately 5–10 out of 30+ variables)
The Lasso Path revealed which indicators consistently entered the model first, identifying the most robust determinants of cross-country economic growth
Regularization methods provide a more credible and interpretable framework for forecasting in macroeconomic datasets with many correlated predictors

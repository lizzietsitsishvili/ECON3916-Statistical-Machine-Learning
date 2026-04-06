NY Fed Yield Curve Recession Model Replication
Objective

Replicate the Federal Reserve Bank of New York’s yield curve–based recession forecasting model using logistic regression to estimate the probability of a U.S. recession 12 months ahead.

Methodology
Collected macroeconomic data from FRED, specifically the 10-Year minus 3-Month Treasury yield spread (T10Y3M) and the NBER recession indicator (USREC), covering 1970 to present.
Resampled daily yield spread data to monthly frequency and constructed a 12-month lag to align with forward-looking recession prediction.
Built a modeling dataset linking lagged yield spreads to future recession outcomes.
Estimated a Linear Probability Model (OLS) as a baseline to highlight its limitations in probabilistic classification.
Implemented logistic regression to model recession probabilities within the [0,1] interval using a nonlinear S-curve.
Extracted and interpreted the odds ratio of the yield spread, including 95% confidence intervals using a statsmodels Logit specification.
Generated a full recession probability time series and compared predictions to actual NBER recession periods.
Key Findings
The Linear Probability Model produces invalid predictions outside the [0,1] range, confirming its unsuitability for binary outcome modeling in this context.
Logistic regression provides well-calibrated, bounded probability estimates and captures the nonlinear relationship between yield curve inversion and recession risk.
The yield spread is a statistically significant predictor: a steeper yield curve substantially reduces the odds of a future recession.
The model successfully identifies elevated recession risk prior to historical downturns (e.g., 2008–2009), demonstrating strong performance as a leading indicator.
During the 2022–2024 inversion period, the model predicted elevated recession probabilities (~40%), yet no NBER recession occurred, illustrating that probabilistic forecasts reflect risk—not certainty—and must be interpreted within broader macroeconomic context.

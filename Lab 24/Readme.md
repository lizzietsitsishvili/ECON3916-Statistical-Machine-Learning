Causal ML — Double Machine Learning for 401(k) Policy Evaluation
Objective

Estimate the causal impact of 401(k) eligibility on household financial assets using modern machine learning methods that correct for selection bias and high-dimensional confounding.

Methodology
Demonstrated regularization bias using a simulated data-generating process, showing that naïve LASSO shrinks the treatment effect toward zero when applied to causal estimation problems
Implemented a Double Machine Learning (DML) Partially Linear Regression (PLR) framework to obtain unbiased causal estimates
Used Random Forest models as nuisance learners to flexibly estimate outcome and treatment functions
Applied 5-fold cross-fitting to separate nuisance estimation from treatment effect estimation and reduce overfitting bias
Defined treatment as 401(k) eligibility and outcome as net total financial assets, controlling for demographic and financial covariates
Estimated the Average Treatment Effect (ATE) and corresponding confidence intervals
Conducted heterogeneity analysis (CATE) by splitting the sample into income quartiles
Visualized treatment effects across income groups to assess variation in policy impact
Key Findings
The estimated Average Treatment Effect (ATE) of 401(k) eligibility on net financial assets was approximately -$867, with a 95% confidence interval of [-$1,810, $76], indicating that the effect is not statistically significant at the 5% level
Results highlight the importance of correcting for selection bias, as naïve comparisons would overestimate the impact due to higher-income individuals being more likely to have access to 401(k) plans
The CATE analysis suggests heterogeneity across income groups, with higher-income households showing stronger responsiveness to 401(k) eligibility, consistent with greater capacity to save and engage with financial instruments
Lower-income households exhibit weaker or negligible responses, reflecting potential constraints such as limited disposable income and lower participation in financial markets
Overall, findings illustrate both the limitations of simple ML approaches (e.g., LASSO) for causal inference and the value of Double Machine Learning in producing more credible policy-relevant estimates

📊 ECON 3916 — Assignment 3: The Causal Architecture
Overview

This project investigates key operational and strategic questions at a simulated logistics platform, SwiftCart Logistics, using non-parametric and causal inference techniques. Traditional statistical assumptions often fail in real-world platform data due to skewness, outliers, and selection bias. This analysis replaces fragile parametric methods with computational approaches to generate more credible insights.

🎯 Objectives
Quantify uncertainty in skewed, zero-inflated data
Evaluate experimental outcomes without relying on parametric assumptions
Identify and correct for selection bias in observational data
Estimate a defensible causal effect using matching techniques
🧠 Methodological Framework
1. Bootstrapping (Non-Parametric Uncertainty)

A zero-inflated and right-skewed distribution of driver tips was simulated to reflect real gig-economy compensation patterns.

Constructed 10,000 bootstrap resamples
Estimated the sampling distribution of the median
Derived a 95% confidence interval using percentiles

Insight:
The resulting confidence interval was asymmetric, highlighting the limitations of parametric methods and demonstrating that bootstrapping better captures uncertainty in skewed environments.

2. Permutation Testing (A/B Test Validation)

An A/B test evaluated a new routing algorithm under conditions where standard assumptions (normality, equal variance) were violated.

Generated control (Normal) and treatment (Log-Normal) groups
Computed observed difference in means
Performed 5,000 random permutations to build an empirical null distribution

Insight:
The permutation test provided an exact, assumption-free p-value, allowing for robust inference despite extreme outliers and heteroscedasticity.

3. Propensity Score Matching (Causal Inference)

The impact of the “SwiftPass” loyalty program was analyzed while addressing selection bias.

Estimated propensity scores using pre-treatment covariates
Matched subscribers to observationally similar non-subscribers
Computed the Average Treatment Effect on the Treated (ATT)

Insight:
The naive difference in spending overstated the program’s effect. Matching reduced bias and produced a more credible causal estimate.

4. Covariate Balance Diagnostics (Love Plot)

To validate the matching procedure, standardized mean differences were compared before and after matching.

Insight:
Post-matching reductions in imbalance demonstrated improved comparability between groups, supporting the validity of the causal estimate.

📈 Key Takeaways
Real-world platform data often violate classical statistical assumptions
Bootstrapping and permutation testing provide robust alternatives to parametric inference
Selection bias can significantly distort conclusions if not addressed
Propensity score matching enables construction of a credible counterfactual
⚠️ Limitations
Matching only accounts for observed covariates; unobserved bias may remain
Synthetic and simulated data may not fully capture real-world complexity
Results depend on correct model specification for propensity scores
🧰 Tools & Technologies
Python (pandas, numpy)
Visualization: matplotlib, seaborn
Machine Learning: scikit-learn

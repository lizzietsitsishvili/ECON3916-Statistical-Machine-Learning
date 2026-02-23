Recovering Experimental Truths via Propensity Score Matching
Objective

This project demonstrates how Propensity Score Matching (PSM) can correct selection bias in observational data and recover credible causal estimates when randomization is absent.

Context

Using the observational subset of the Lalonde dataset, I examined how naive comparisons between treatment and control groups can produce severely biased causal estimates due to non-random program participation. The observational sample exhibits strong pre-treatment imbalance, making it a useful test case for evaluating bias correction methods.

Methodology

To reconstruct experimental credibility, I implemented a structured causal adjustment pipeline:

Modeled Selection Bias

Built logistic regression models to estimate the probability of treatment assignment.

Used pre-treatment covariates to capture systematic differences between treated and control units.

Explicitly treated selection into job training as a non-random process requiring modeling.

Estimated Propensity Scores

Computed predicted treatment probabilities (propensity scores) using Scikit-Learn.

Diagnosed overlap and common support to ensure feasible matching.

Treated propensity scores as a dimensionality-reduction mechanism for balancing covariates.

Applied Nearest Neighbor Matching

Implemented nearest-neighbor matching to pair treated observations with statistically similar controls.

Reduced covariate imbalance prior to outcome comparison.

Constructed a matched sample approximating the conditions of a randomized experiment.

All implementation was conducted using Python, Pandas, and Scikit-Learn.

Key Findings

The naive observational estimate suggested a large negative treatment effect of approximately –$15,204, reflecting severe selection bias.

After applying Propensity Score Matching, I recovered a treatment effect of approximately +$1,800, closely aligning with the true experimental benchmark.

This shift illustrates how uncorrected observational comparisons can invert causal conclusions, and how structured bias adjustment can restore experimental truth.

Professional Insight

Selection bias is not a minor statistical inconvenience — it is a structural distortion.

Propensity Score Matching functions as a causal repair mechanism, reconstructing counterfactual comparability when randomized control is unavailable. In applied economic and policy settings, this distinction separates misleading correlation from defensible causal inference.

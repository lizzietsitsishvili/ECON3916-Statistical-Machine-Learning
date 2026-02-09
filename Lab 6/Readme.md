# 🧠 Lab 5: The Architecture of Bias  
## Generating the Signals — Sampling Error, Covariate Shift, SRM & Ghost Data

## Objective

This project investigates how bias enters machine learning systems through flawed **Data Generating Processes (DGPs)** and improper sampling and selection mechanisms.

Rather than focusing solely on predictive accuracy, this lab analyzes how structural distortions arise from:

- Sampling variance  
- Distribution imbalance  
- Experimental allocation errors  
- Conditional observability (selection bias)  

The central insight:

> Bias is often architectural, not algorithmic.

---

## Statistical & Experimental Context

Machine learning models are only as reliable as the processes that generate their data.

Bias can emerge from:

1. **Finite sampling noise** (random fluctuation)
2. **Covariate shift** (imbalanced class distributions)
3. **Engineering failures in experiments** (Sample Ratio Mismatch)
4. **Selection bias** (missing counterfactual populations)

This project empirically isolates and analyzes each of these mechanisms.

---

## Methodology

### 1️⃣ Sampling Variance — Simple Random Sampling

Using the Titanic dataset, I simulated repeated Simple Random Sampling (SRS) to quantify how much estimates fluctuate purely due to randomness.

Approach:
- Randomly sampled subsets (n = 80)
- Repeated sampling 500 times
- Measured distribution of survival rate estimates

Result:
Even under perfect randomness, small samples exhibit meaningful dispersion.

Key takeaway:

> Not all variation is bias — some is statistical noise.

---

### 2️⃣ Covariate Shift — Stratified vs Non-Stratified Splits

I compared standard train/test splitting against stratified sampling using `sklearn`.

Non-stratified splits may distort class proportions in imbalanced datasets, leading to misleading performance metrics.

Stratified sampling preserves label distributions across splits, improving evaluation reliability.

Key takeaway:

> Dataset splitting is a structural design choice with statistical consequences.

---

### 3️⃣ Experimental Forensics — Sample Ratio Mismatch (SRM)

In a simulated A/B test with a planned 50/50 allocation, I observed a 55/45 traffic split (450 vs 550 users).

Using a Chi-Square goodness-of-fit test (`scipy.stats.chisquare`), I tested whether this deviation was statistically plausible under true random assignment.

The results indicated significance at the 1% level, suggesting the imbalance was unlikely due to chance.

Potential causes include:
- Load balancer misconfiguration
- Randomization logic errors
- Tracking or instrumentation failures

Key takeaway:

> Before interpreting treatment effects, validate the integrity of the assignment mechanism.

---

### 4️⃣ Selection Bias & “Ghost Data” — Heckman Framework

To analyze structural selection bias, I explored a Heckman-style two-step correction.

#### The Problem

Analyzing only successful Unicorn startups featured on TechCrunch creates **Survivorship Bias**.

We observe:
- Firms that survived
- Firms that scaled
- Firms that received media coverage

We do not observe:
- Failed startups
- Firms that shut down quietly
- Companies that never received press

This missing counterfactual population is the **Ghost Data**.

#### The Correction

The Heckman framework corrects selection bias by:

1. Modeling the probability of being observed (selection equation)
2. Computing the Inverse Mills Ratio (IMR)
3. Including the IMR term in the outcome regression

This allows estimation of outcome relationships while accounting for non-random selection into the dataset.

Key takeaway:

> Selection bias is a modeling problem only if the selection mechanism is ignored.

---

## Key Findings

- Sampling variance can produce large fluctuations in small datasets.
- Improper train/test splits introduce artificial distribution shifts.
- A 55/45 experimental split is statistically unlikely under true randomization.
- Observational datasets conditioned on success systematically overestimate predictor importance.
- Correcting for selection requires modeling the missing population.

---

## Broader Implications

This analysis highlights parallels between:

- Survivorship bias in hedge fund databases
- Startup visibility bias in venture ecosystems
- Selection bias in credit risk modeling
- Allocation errors in growth experimentation

Understanding bias at the data-generating level is critical for:

- Reliable causal inference
- Robust financial modeling
- Trustworthy AI deployment
- Ethical machine learning systems

---

## Technical Skills Demonstrated

- Monte Carlo simulation
- Sampling distribution analysis
- Stratified dataset construction
- Chi-Square hypothesis testing
- Econometric selection modeling (Heckman framework)
- Bias diagnosis in experimental systems

---

*This project demonstrates how econometric reasoning and statistical validation can be applied to diagnose structural bias in modern machine learning pipelines.*

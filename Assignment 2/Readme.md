# Audit 02: Deconstructing Statistical Lies

This audit shows how “good-looking” metrics can hide real-world risk. I recreated three common statistical traps using manual calculations (where required) and simulations in Python.

---

## 1) Robustness Audit — Latency Skew (The “Mean Latency” Trap)

**Claim:** “NebulaCloud has a mean latency of 35ms.”  
**Audit finding:** In a skewed (Pareto-like) system, the **mean can be a vanity metric**.

### What I simulated
- **1,000 requests total**
- **980 normal requests:** 20–50ms  
- **20 spike requests:** 1000–5000ms

### Key takeaway
- **Standard Deviation (SD) explodes** because it squares large deviations, so a few extreme spikes dominate the metric.
- **Median Absolute Deviation (MAD) stays stable** because it relies on medians, which are resistant to outliers.

**Conclusion:** Average latency can look fine while users experience severe tail latency.

---

## 2) Probability Audit — False Positive Paradox (Base Rate Fallacy)

**Claim:** “IntegrityAI is 98% accurate (Sensitivity=98%, Specificity=98%).”  
**Audit finding:** With a low base rate, most flags can still be false positives.

### Method
I calculated:
\[
P(\text{Cheater} \mid \text{Flagged})
\]
using Bayes’ Rule with a function `bayesian_audit(prior, sensitivity, specificity)`.

### Scenarios tested
- **Bootcamp:** base rate = 50%  
- **Econ class:** base rate = 5%  
- **Honors seminar:** base rate = 0.1%

**Conclusion:** Even a strong detector produces mostly false positives when cheating is rare.

---

## 3) AI Expansion — Survivorship Bias (The Memecoin Graveyard)

**Problem:** Platforms often highlight “winners” and erase failures.  
On Pump.fun–style launch dynamics, the majority of tokens fail, so analyzing only “listed coins” is misleading.

### What I simulated
- **10,000 token launches**
- **Peak market cap** drawn from a **Pareto (power-law) distribution**
- Two datasets:
  - `df_all`: all tokens (the graveyard)
  - `df_survivors`: top 1% only (the “survivors”)

### Result
I compared the mean market cap of:
- **All tokens** vs.
- **Top 1% survivors**

**Conclusion:** The “survivors-only” dataset greatly inflates average performance, demonstrating survivorship bias.

---

## Tools Used
- Python (NumPy, Pandas, Matplotlib)
- Manual calculations required by assignment (MAD, chi-square loop, Bayes posterior)

---

## Files
- `Econ_3916_Assignment_2_Audit.ipynb` — full code + outputs
If you want, paste your actual numeric outputs (mean latency, SD, MAD, the three posteriors, mean market caps for all vs survivors) and I’ll help you add a tiny “Results Snapshot” section so your README looks even more polished.


You said:
yes

ChatGPT said:
Perfect — here’s a stronger, portfolio-level README with a clean Results Snapshot section.

Just replace the bracketed numbers with your actual outputs.

# Audit 02: Deconstructing Statistical Lies

This audit investigates how common statistical metrics can mislead decision-makers.  
Using manual calculations and simulations, I examined robustness failures, base rate distortions, and survivorship bias in modern digital systems.

---

# 1) Robustness Audit — Latency Skew

### Scenario
“NebulaCloud” claims a mean latency of 35ms.

### Simulation
- 1,000 total requests
- 980 normal requests (20–50ms)
- 20 spike requests (1000–5000ms)

### Results Snapshot
- **Mean Latency:** [insert mean]
- **Median Latency:** [insert median]
- **Standard Deviation (SD):** [insert SD]
- **Median Absolute Deviation (MAD):** [insert MAD]
- **P99 Latency:** [insert p99]

### Insight
The SD is inflated by extreme spike requests because it squares deviations.  
The MAD remains stable because medians are robust to outliers.

**Conclusion:** Mean latency hides tail risk. Real user experience is driven by extreme events, not averages.

---

# 2) Probability Audit — False Positive Paradox

### Scenario
IntegrityAI claims 98% accuracy (Sensitivity = 98%, Specificity = 98%).

I calculated:

P(Cheater | Flagged)

using Bayes' Rule across different base rates.

### Results Snapshot
- **Bootcamp (50% base rate):** [insert %]
- **Econ Class (5% base rate):** [insert %]
- **Honors Seminar (0.1% base rate):** [insert %]

### Insight
When cheating is rare, even highly accurate systems produce mostly false positives.

**Conclusion:** Accuracy without base rate context is misleading.

---

# 3) Survivorship Bias — The Memecoin Graveyard

### Scenario
Most crypto tokens fail. Platforms highlight survivors.

### Simulation
- 10,000 token launches
- Pareto (power-law) distributed peak market caps
- Compared:
  - `df_all` (all tokens)
  - `df_survivors` (top 1%)

### Results Snapshot
- **Mean Market Cap (All Tokens):** [insert value]
- **Mean Market Cap (Top 1%):** [insert value]
- **Survivorship Multiplier:** [insert X]x

### Insight
Analyzing only surviving tokens dramatically inflates perceived average performance.

**Conclusion:** Selection bias creates statistical illusions of success.

---

# Key Takeaways

- Robust statistics (MAD, percentiles) outperform averages in skewed systems.
- Base rates determine posterior truth, not model “accuracy.”
- Selection bias can completely distort financial narratives.

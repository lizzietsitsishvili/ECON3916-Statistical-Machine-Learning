# The Cost of Living Crisis: A Data-Driven Analysis

## The Problem

Official inflation statistics suggest that inflation is cooling. However, many students still feel persistent financial pressure.

The reason is that the Consumer Price Index (CPI) reflects the “average” American consumer — not a full-time student.

Students allocate a larger share of their budgets to tuition, rent, and food away from home. When those categories rise faster than the national average, students experience a different inflation reality.

This project tests that hypothesis.

---

## Methodology

This analysis was conducted in Python using:

- `pandas` for data processing  
- `matplotlib` for visualization  
- `fredapi` to access Federal Reserve Economic Data (FRED)

### Data Sources

- CPIAUCSL — Official U.S. CPI  
- CUSR0000SEEB — Tuition  
- CUSR0000SEHA — Rent  
- CUSR0000SERA02 — Cable & Streaming  
- CUSR0000SEFV — Food Away From Home  

### Index Construction (Laspeyres Framework)

All series were normalized to a common base year:

**2016 = 100**

Re-indexing removes distortions from differing historical base years and allows direct comparison of growth rates.

A custom **Student Spending Price Index (Student SPI)** was constructed using fixed student-relevant weights.

---

## Key Findings

- Official CPI (since 2016): XX%  
- Student SPI (since 2016): XX%  
- Divergence: XX percentage points  

The results show that student-relevant costs have risen faster than the national CPI basket, primarily driven by tuition, rent, and food away from home.

---

## Why Normalization Matters

Raw CPI component series use different base years (e.g., 1982=100 vs 2002=100). Plotting raw index levels together creates misleading conclusions because differences in scale reflect base-year construction rather than true growth.

Re-indexing to a common baseline ensures we compare growth rates rather than arbitrary index levels.

---

## Tools Used

Python | pandas | matplotlib | FRED API

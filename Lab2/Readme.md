# The Illusion of Growth & the Composition Effect

## Objective
This project investigates long-run wage stagnation in the United States by correcting nominal wage data for inflation and identifying statistical distortions that can misrepresent labor market strength. Using live data from the Federal Reserve Economic Data (FRED) API, the analysis aims to distinguish real wage growth from *illusory* increases driven by compositional changes in the workforce.

## Methodology

### Data Ingestion (FRED API)
A Python-based data pipeline was built to retrieve and process live macroeconomic time series from the FRED database using the `fredapi` library. The primary datasets include:

- **Average Hourly Earnings of Total Private Industries (AHETPI)** – nominal wage measure  
- **Consumer Price Index (CPI)** – used to deflate nominal wages  
- **Employment Cost Index (ECI)** – composition-adjusted labor cost measure  

### Inflation Adjustment
Nominal wages were deflated using CPI to compute **Real Wages**, allowing for a consistent comparison of purchasing power over time and eliminating the effects of inflation.

### Anomaly Detection: The Pandemic Spike
An apparent surge in real wages during 2020 was identified. Rather than interpreting this as a genuine increase in labor demand, the project examined whether this spike reflected a **statistical artifact**.

### Composition Effect Correction
To control for changes in workforce composition during the COVID-19 pandemic, the Employment Cost Index (ECI) was incorporated. Because ECI adjusts for shifts in worker demographics and job types, it provides a more accurate measure of underlying labor cost trends. Comparing real wages to ECI revealed that the 2020 spike was not structural.

## Key Findings: The Pandemic Paradox

- **The Money Illusion:** Despite steady increases in nominal wages, real wages have remained largely flat over the past 50 years, highlighting the disconnect between headline earnings growth and actual purchasing power.
- **The Pandemic Paradox:** The sharp rise in average wages during 2020 was driven by low-wage workers disproportionately exiting the labor force, mechanically raising the average wage. ECI data confirms that this was not a true increase in labor demand or worker compensation.
- **Conclusion:** The perceived wage boom during the pandemic was a statistical illusion caused by the **composition effect**, underscoring the importance of adjusting for both inflation and workforce structure when analyzing economic data.


# The Architecture of Dimensionality: Hedonic Pricing & the FWL Theorem

## Objective  
Develop and validate a multivariate hedonic pricing model to quantify real estate valuation drivers while formally demonstrating the Frisch-Waugh-Lovell (FWL) theorem as a mechanism for isolating causal effects.

## Methodology  
- Constructed a multivariate Ordinary Least Squares (OLS) regression model predicting Sale_Price using Property_Age and Distance_to_Tech_Hub  
- Estimated a naive univariate model to establish a baseline and identify potential bias  
- Applied the Frisch-Waugh-Lovell (FWL) theorem by:  
  - Regressing each variable on the control variable  
  - Extracting residuals to remove shared covariance  
  - Regressing residualized variables to isolate partial effects  
- Verified that the FWL-derived coefficient exactly matched the multivariate OLS estimate  

## Key Findings  
The naive model exhibited strong omitted variable bias, overstating the effect of property age on sale price due to its correlation with proximity to tech hubs. After controlling for Distance_to_Tech_Hub, the model corrected this distortion. The FWL theorem provided a precise decomposition of this bias, isolating the true independent effect of each variable and demonstrating how multivariate regression enforces ceteris paribus conditions.

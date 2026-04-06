# AI Capex Diagnostic Modeling

## Objective
This project analyzes an OLS regression model predicting AI Software Revenue and evaluates whether the model assumptions are violated due to heteroscedasticity and multicollinearity.

## Methodology
- Loaded and cleaned the Nvidia AI Capex dataset using pandas.
- Built a baseline OLS regression model using statsmodels.
- Evaluated model performance using R-squared and p-values.
- Conducted residual analysis by plotting residuals against fitted values.
- Applied the White Test to formally test for heteroscedasticity.
- Calculated Variance Inflation Factors (VIF) to detect multicollinearity.
- Re-estimated the model using HC3 robust standard errors to correct inference issues.

## Key Findings
The initial OLS model showed very high R-squared and extremely low p-values, suggesting strong statistical significance. However, residual analysis revealed clear heteroscedasticity, especially at higher levels of capital expenditure. The White Test confirmed this issue statistically. After applying HC3 robust standard errors, the estimated standard errors increased, and the statistical significance of some variables became weaker. This indicates that the original model results were overly optimistic due to heteroscedasticity.

## Tools Used
Python, pandas, statsmodels, matplotlib, seaborn

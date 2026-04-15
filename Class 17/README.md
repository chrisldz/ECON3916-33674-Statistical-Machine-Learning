# NY Fed Yield Curve Recession Model Replication

## Objective
This project replicates the Federal Reserve Bank of New York’s recession probability model using logistic regression on macroeconomic data, aiming to predict the likelihood of a U.S. recession 12 months ahead.

## Methodology
- Collected macroeconomic data from FRED, including the 10-year minus 3-month Treasury yield spread (T10Y3M) and the NBER recession indicator (USREC).
- Resampled daily yield spread data to monthly frequency and aligned it with the recession indicator.
- Applied a 12-month lag to the yield spread to match the forecasting setup used by the NY Fed.
- Estimated a Linear Probability Model (OLS) to highlight its limitations for binary outcomes.
- Fitted a logistic regression model using scikit-learn to generate bounded probability predictions.
- Used statsmodels to extract coefficient estimates, standard errors, and 95% confidence intervals.
- Computed and interpreted the odds ratio to explain the economic meaning of the model.
- Generated a time series of predicted recession probabilities and visualized it with recession shading.

## Key Findings
The results show that the Linear Probability Model produces unrealistic predictions below 0 and above 1, confirming it is not appropriate for binary outcomes. In contrast, the logistic regression model generates a smooth S-shaped probability curve that stays within the valid range. The estimated odds ratio indicates that an increase in the yield spread reduces the odds of a recession, which is consistent with economic intuition. During the 2022–2024 yield curve inversion period, the model predicted high recession probabilities, but no recession occurred, suggesting that the model captures risk rather than certainty and should be interpreted probabilistically rather than deterministically.

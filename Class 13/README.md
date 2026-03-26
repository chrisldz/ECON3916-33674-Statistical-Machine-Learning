# The Architecture of Dimensionality: Hedonic Pricing & the FWL Theorem

## Objective
This project builds a multivariate hedonic pricing model to estimate housing prices and shows how controlling for confounding variables changes the interpretation of coefficients.

## Methodology
- Loaded and explored a California housing dataset using pandas.
- Ran a simple OLS regression of Sale_Price on Property_Age to observe the naive relationship.
- Extended the model by adding Distance_to_Tech_Hub to control for location effects.
- Compared the change in the coefficient of Property_Age between the naive and multivariate models.
- Manually implemented the Frisch-Waugh-Lovell (FWL) theorem:
  - Regressed Sale_Price on Distance_to_Tech_Hub and saved residuals.
  - Regressed Property_Age on Distance_to_Tech_Hub and saved residuals.
  - Ran a regression of price residuals on age residuals without intercept.
- Verified that the FWL coefficient matches the multivariate regression coefficient.

## Key Findings
The results show strong omitted variable bias in the naive model. Property_Age appeared to have a misleading effect on housing prices when Distance_to_Tech_Hub was not included. After controlling for location, the coefficient changed significantly, showing that part of the effect was actually coming from the omitted variable. The FWL theorem confirmed this by isolating the true relationship and producing the same coefficient as the full model.

## Interpretation
This project shows that regression results can be misleading if important variables are omitted. By controlling for confounders, the model gives a more accurate estimate of the relationship. The FWL theorem provides a clear way to understand how regression isolates partial effects.

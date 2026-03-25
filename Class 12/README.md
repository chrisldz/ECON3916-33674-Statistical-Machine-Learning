# Architecting the Prediction Engine

## Objective  
Build a multivariate OLS prediction model to estimate housing values and evaluate predictive performance using RMSE.

## Methodology  
- Loaded the Zillow ZHVI 2026 Micro dataset into a pandas DataFrame  
- Used the Patsy formula interface in statsmodels to specify an OLS model with Home_Value as the dependent variable  
- Regressed housing values on Square_Footage, Property_Age, and Distance_to_Transit  
- Fit the model and reviewed the summary table to interpret coefficients and model fit  
- Generated predicted housing values using the fitted model  
- Calculated RMSE to measure the average prediction error in US dollars  
- Built a residual forensics plot to visualize errors and detect potential outliers or heteroscedasticity  

## Key Findings  
- The OLS model provides both economic interpretation and predictive capability  
- The RMSE gives a clear measure of how large the prediction errors are in real dollar terms  
- The residual plot shows whether errors are randomly distributed or increase with predicted values  
- Some patterns in residuals may suggest heteroscedasticity or structural issues in the model

# High-Dimensional GDP Growth Forecasting with Lasso and Ridge Regularization

## Objective
This project analyzes how to predict 5-year average GDP per capita growth using high-dimensional World Bank data, while addressing overfitting through regularization techniques.

## Methodology
- Collected 36 World Development Indicators (WDI) for around 150 countries (2013–2019) using the World Bank API.
- Constructed a cross-sectional dataset by averaging values over time.
- Split the data into training and test sets to evaluate out-of-sample performance.
- Implemented Ordinary Least Squares (OLS) as a baseline model.
- Applied Ridge and Lasso regression with cross-validated lambda (λ) selection.
- Standardized features to ensure proper regularization.
- Visualized the Lasso path to examine how variables enter the model as the penalty decreases.

## Key Findings
- OLS showed strong overfitting, with training R² close to 1 but much lower test R², indicating poor generalization.
- Ridge regression reduced variance by shrinking coefficients, improving test performance.
- Lasso produced a sparse model by selecting a small subset of predictors, while achieving similar or better test R² than Ridge.
- The Lasso path revealed that a few key indicators (such as development and institutional variables) enter the model first, suggesting they are the most robust predictors of GDP growth.
- Variables set to zero by Lasso are not necessarily economically irrelevant, but often redundant given the correlation structure of the data.

## Tools
Python, wbapi, scikit-learn (LinearRegression, RidgeCV, LassoCV), numpy, pandas, matplotlib

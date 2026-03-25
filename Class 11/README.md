# Data Wrangling & Engineering Pipeline

## Objective

Prepare a messy real-world dataset for econometric analysis by diagnosing missing data patterns, performing conditional imputation, and applying appropriate encoding methods.

## Methodology

* Conducted initial data audit using pandas to inspect data types and missing values
* Used missingno to visualize missingness and identify a MAR structure
* Imputed missing `base_salary` values using median within each department group
* Applied one-hot encoding to categorical variables and demonstrated the Dummy Variable Trap
* Resolved multicollinearity by using k-1 encoding (dropping a reference category)
* Implemented target encoding to reduce high-cardinality `office_zip` into a continuous variable

## Key Findings

* Missing data followed a structured MAR pattern rather than random noise
* Improper dummy encoding led to perfect multicollinearity and model failure
* Dropping a reference category successfully resolved the Dummy Variable Trap
* Target encoding effectively compressed high-cardinality features while preserving useful information

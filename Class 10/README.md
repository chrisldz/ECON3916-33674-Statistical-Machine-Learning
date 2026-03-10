# Structural Forensics of Macroeconomic Data

## Overview

This project investigates the dangers of spurious correlation and multicollinearity in macroeconomic time-series data using variables from the Federal Reserve Economic Data (FRED) API. Raw macroeconomic indicators often exhibit strong correlations due to shared long-term trends rather than meaningful causal relationships.

## Methodology

First, I collected a small set of macroeconomic indicators including CPI, unemployment rate, federal funds rate, industrial production, and M2 money supply. A correlation heatmap was used to visualize the misleading relationships present in the raw level data.

To diagnose multicollinearity, I calculated the Variance Inflation Factor (VIF) for the explanatory variables. The high VIF values confirmed that many variables contain redundant information driven by common macroeconomic trends.

To address this issue, I transformed the non-stationary variables into Year-over-Year (YoY) growth rates. This transformation removes long-run trends and focuses the analysis on short-term structural changes.

Finally, a Directed Acyclic Graph (DAG) framework was used to conceptualize the causal structure between monetary policy variables and inflation dynamics.

## Key Insight

The analysis demonstrates how raw correlations in macroeconomic data can be misleading. By applying proper transformations and causal reasoning tools, it becomes possible to distinguish structural relationships from trend-driven statistical artifacts.

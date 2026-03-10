# Causal Inference in Platform Data

## Overview

This project applies causal inference methods to analyze decision-making problems in a logistics platform environment. The goal is to separate true causal effects from misleading correlations caused by skewed data distributions and selection bias.

## Phase 1 – Bootstrapping

Driver tip data is highly zero-inflated and right-skewed. To estimate uncertainty without assuming normality, a manual bootstrap procedure was implemented. By repeatedly resampling the data and computing the median, an empirical confidence interval was constructed.

## Phase 2 – Permutation Test

An A/B test was simulated to evaluate a routing algorithm. Because the treatment data contains extreme outliers, a permutation test was used instead of a traditional t-test. This method builds an empirical null distribution and produces a more reliable p-value.

## Phase 3 – Propensity Score Matching

A naive comparison suggested that subscribers spend more than non-subscribers. However, this is driven by selection bias. Propensity Score Matching was used to match users with similar characteristics and estimate a more credible treatment effect.

## Phase 4 – Covariate Balance

A Love Plot was generated to compare standardized mean differences before and after matching. The results show improved covariate balance, indicating that the matching process successfully reduced selection bias.

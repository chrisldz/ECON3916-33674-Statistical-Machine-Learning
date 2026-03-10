# Recovering Experimental Truths via Propensity Score Matching

## Project Title

Recovering Experimental Truths via Propensity Score Matching

## Objective

This project demonstrates how Propensity Score Matching (PSM) can correct selection bias in observational data and recover credible estimates of causal treatment effects.

## Methodology

* **Selection Bias Diagnosis**
  I first replicated the classic “observational failure” by computing the raw difference in earnings between individuals who received job training and those who did not. The naive comparison misleadingly suggested that the training program reduced earnings, illustrating how non-random participation distorts causal inference.

* **Propensity Score Estimation**
  To address this bias, I estimated each individual's probability of receiving training using a logistic regression model based on observable characteristics such as demographics and prior earnings. These predicted probabilities serve as the **propensity scores**, summarizing the likelihood of treatment assignment.

* **Nearest-Neighbor Matching**
  Using these scores, I implemented one-to-one nearest-neighbor matching. Each treated individual was paired with a control individual who had a similar probability of participating in the program. This procedure constructs a balanced comparison group that approximates the conditions of a randomized experiment.

* **Post-Matching Evaluation**
  After matching, the treatment and control groups were re-compared. By aligning individuals with similar observable characteristics, the analysis reduces confounding and produces a more credible estimate of the causal effect.

## Key Findings

The naive observational estimate suggested a strongly negative treatment effect due to severe selection bias. After applying Propensity Score Matching, the estimated effect shifted dramatically and recovered a positive earnings impact of approximately **+$1,800**.

This result closely aligns with the findings from the original randomized Lalonde experiment, demonstrating how careful causal inference techniques can reconstruct experimental insights from observational data.

## Interpretation

This exercise highlights a fundamental lesson in applied econometrics: **observational comparisons can produce deeply misleading conclusions when treatment assignment is not random**. Propensity Score Matching provides a structured way to approximate experimental balance, allowing analysts to isolate causal signals from biased observational data.

In practice, such methods are critical for policy evaluation, product experimentation, and data-driven decision-making in environments where randomized experiments are unavailable or impractical.

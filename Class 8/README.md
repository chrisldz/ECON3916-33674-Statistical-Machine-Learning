# Hypothesis Testing & Causal Evidence Architecture

## Project Overview

This lab operationalizes the scientific method within a modern data science workflow. Using the Lalonde (1986) randomized experiment, I moved beyond descriptive estimation and into formal falsification. Rather than asking “What is the average treatment effect?”, the core question became: *Can we statistically reject the null narrative that job training has no impact on earnings?*

This shift from estimation to falsification reframes causal analysis as a disciplined process of ruling out randomness.

---

## Objective

The objective of this lab was to adjudicate between competing causal narratives using a randomized benchmark dataset. By leveraging experimental data, I tested whether the observed lift in post-training earnings reflects genuine treatment impact or statistical noise.

This project emphasizes that causal claims must survive structured attempts at refutation.

---

## Technical Approach

* **Signal-to-Noise Decomposition:**
  Computed the Average Treatment Effect (ATE) as the difference in group means and interpreted the Welch’s T-Statistic as a formal Signal-to-Noise Ratio.

* **Parametric Inference (Welch’s T-Test):**
  Applied unequal-variance testing to account for heteroskedastic earnings distributions.

* **Non-Parametric Validation (Permutation Test, 10,000 Resamples):**
  Constructed an empirical null distribution by shuffling treatment labels, stress-testing the parametric result against distributional assumptions.

* **Type I Error Control:**
  Adopted α = 0.05 as a predefined rejection threshold to guard against false discoveries.

---

## Key Findings

The analysis identified a statistically significant increase in 1978 real earnings of approximately **$1,795** for treated individuals. Both the parametric and permutation tests rejected the null hypothesis, suggesting that the observed lift is unlikely to be due to chance alone.

The convergence of results across inference methods strengthens the credibility of the causal estimate.

---

## Business Insight

Rigorous hypothesis testing functions as a safety valve in the algorithmic economy. Without formal falsification frameworks, organizations risk mistaking noise for signal — leading to data dredging, spurious correlations, and overconfident product decisions.

Controlled inference — especially when validated with non-parametric methods — ensures that strategic decisions are grounded in reproducible statistical evidence rather than narrative momentum.

In high-stakes environments, statistical discipline is not academic formality; it is operational risk management.

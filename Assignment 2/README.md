# Audit 02: Deconstructing Statistical Lies

## Executive Summary

This audit investigates how statistical summaries can mislead decision-makers when distributional structure, base rates, and selection effects are ignored. Through three controlled simulations — Latency Skew, False Positives, and Survivorship Bias — we demonstrate how common metrics distort reality under heavy-tailed and imbalanced conditions.

The central finding: **Statistical metrics are only as honest as the assumptions behind them.**

---

## 1. Latency Skew — The Illusion of the Mean

### Simulation Design

* 1,000 server requests
* 980 “normal” latencies (20–50ms)
* 20 extreme spikes (1000–5000ms)

This creates a highly skewed distribution with a long right tail.

### Findings

* The **mean latency increases materially** due to a small number of extreme values.
* The **standard deviation explodes**, since it squares deviations.
* The **median and MAD remain stable**, reflecting the central mass of the data.

### Insight

In skewed systems (e.g., cloud infrastructure), the mean becomes a vanity metric. It obscures tail risk and understates operational volatility. Robust statistics (median, MAD) better capture system stability.

---

## 2. False Positives — The Base Rate Paradox

### Scenario

A plagiarism detection system claims:

* Sensitivity = 98%
* Specificity = 98%

However, cheating prevalence (base rate) is only 0.1%.

### Bayesian Evaluation

Using Bayes’ Theorem:

[
P(Cheater \mid Flagged) =
\frac{Prior \cdot Sensitivity}
{Prior \cdot Sensitivity + (1 - Prior)(1 - Specificity)}
]

### Findings

Despite high accuracy:

* The majority of flagged cases are false positives.
* Posterior probability collapses under low base rates.

### Insight

Accuracy metrics without context are deceptive. In rare-event environments, even highly accurate systems generate mostly false alarms. Base rates dominate inference.

---

## 3. Survivorship Bias — The Crypto Mirage

### Simulation Design

* 10,000 token launches
* Market caps generated via a Pareto (power-law) distribution
* Top 1% labeled as “survivors”

### Findings

* The survivor group exhibits dramatically higher mean market cap.
* The overall population mean is far lower.
* Most tokens cluster near zero.

### Insight

Analyzing only surviving assets inflates perceived returns and risk-adjusted performance. Survivorship bias systematically exaggerates success rates in venture, crypto, and hedge fund analyses.

---

## Cross-Case Pattern

Across all three audits, the same structural distortion appears:

| Distortion Type   | Mechanism                 | Resulting Illusion    |
| ----------------- | ------------------------- | --------------------- |
| Latency Skew      | Heavy-tailed distribution | Mean understates risk |
| False Positives   | Low base rate             | Accuracy overstated   |
| Survivorship Bias | Selective observation     | Returns overstated    |

Each case demonstrates how summary metrics detach from reality when structural assumptions are violated.

---

## Conclusion

Statistical deception rarely stems from false data. It emerges from:

* Ignoring distribution shape
* Ignoring base rates
* Ignoring missing observations

Robust analysis requires auditing assumptions before trusting metrics.

In complex systems — financial markets, AI detection models, infrastructure performance — distribution-aware reasoning is not optional. It is foundational.

# Lab 5: The Architecture of Bias

## Project Overview

This lab investigates how bias enters machine learning systems through the **Data Generating Process (DGP)** and improper sampling.

The objective was to move beyond model performance and examine how upstream data decisions introduce systematic error before a model is even trained.

This project demonstrates how sampling bias, covariate shift, and engineering failures can corrupt experimental validity — even when models are correctly implemented.

---

## Tech Stack

* Python
* pandas
* numpy
* scipy (Chi-Square testing)
* scikit-learn

---

## Methodology

### 1️⃣ Simple Random Sampling (High Variance Simulation)

Using the Titanic dataset, I manually implemented a **shuffle-and-split** procedure with `numpy` to simulate Simple Random Sampling (SRS).

* Performed an 80/20 manual split.
* Compared survival rates across train and test sets.
* Observed measurable delta caused purely by randomness.

This demonstrated:

> Randomness does not guarantee representativeness.
> Small samples produce sampling error and unstable distributions.

---

### 2️⃣ Stratified Sampling (Eliminating Covariate Shift)

To correct the imbalance, I implemented **Stratified Sampling** using `sklearn.train_test_split`.

* Stratified by passenger class (`pclass`)
* Enforced identical class distributions across train and test sets
* Removed unintended covariate shift

This showed how:

> Structural control over the sampling process reduces variance and stabilizes inference.

---

### 3️⃣ Sample Ratio Mismatch (SRM) Forensic Audit

I simulated an A/B experiment with a planned 50/50 split that produced a 450/550 allocation.

Using `scipy.stats.chisquare`, I conducted a Chi-Square test to detect whether the imbalance was due to natural variance or engineering failure.

Result interpretation:

* If p < 0.01 → Sample Ratio Mismatch detected
* Indicates possible load balancer, routing, or logging errors

This phase emphasized:

> Statistical testing can detect infrastructure bias before model bias appears.

---

## Key Concepts Demonstrated

* Data Generating Process (DGP)
* Sampling Error
* Covariate Shift
* Stratified Sampling
* Experimental Forensics (SRM detection)
* Structural vs Random Bias

---

# Theoretical Reflection

## Why does analyzing only successful Unicorn startups create Survivorship Bias?

If we analyze only Unicorn startups featured on TechCrunch, we observe only **survivors** — companies that reached extreme success.

However, we ignore:

* The thousands of startups that failed
* The ventures that raised funding but never scaled
* The companies that pivoted unsuccessfully

This creates **Survivorship Bias**, because:

* We condition on success.
* We observe outcomes only from one tail of the distribution.
* We mistakenly infer that observed traits (e.g., aggressive growth, elite founders, AI branding) cause success.

In reality:

> These traits may also exist in failed startups.
> We just do not see them.

This leads to inflated causal conclusions and distorted strategic inference.

---

## What Ghost Data is required for a Heckman Correction?

To correct for selection bias using a **Heckman Two-Step Model**, we need data on:

### 👻 The Ghost Data (Unobserved Failures)

Specifically:

1. Data on startups that failed or never became Unicorns
2. Their funding levels, team structure, growth rate, sector, etc.
3. A variable that affects *selection into TechCrunch coverage* but does not directly affect startup performance (exclusion restriction)

Examples of Ghost Data:

* All startups founded in the same period (not just Unicorns)
* VC-backed companies that exited below $1B
* Startups that shut down
* Private firm registry data

Without observing this missing population, we cannot model the **selection equation**, which is required for Heckman correction.

---

## Structural Insight

Survivorship Bias is not a modeling problem.

It is a **selection problem in the Data Generating Process**.

Heckman correction works only if:

* We can observe both selected and non-selected units.
* We model the probability of being observed.

If the failures are invisible, correction is impossible.

---

# Final Takeaway

Bias is architectural.

It originates in:

* Data collection
* Sampling design
* Selection mechanisms
* Infrastructure failures

Machine learning models inherit the structure of the data they are fed.

Before optimizing algorithms, we must audit the data pipeline.

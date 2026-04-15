# Fraud Detection Model Evaluation — Metrics that Matter

## Objective
Evaluate a logistic regression fraud detection model beyond accuracy by applying confusion matrices, Precision, Recall, F1-Score, ROC and Precision-Recall curves, and threshold analysis on a highly imbalanced dataset.

## Methodology
- Loaded the Kaggle Credit Card Fraud dataset (284,807 transactions, 0.172% fraud rate)
- Prepared features by removing non-informative variables and scaling the transaction amount
- Trained a Logistic Regression classifier using scikit-learn
- Computed predicted probabilities and evaluated performance at multiple thresholds
- Constructed confusion matrices to analyze True Positives, False Positives, False Negatives, and True Negatives
- Calculated Precision, Recall, and F1-Score with a focus on the fraud class
- Plotted ROC and Precision-Recall curves and computed ROC-AUC and PR-AUC
- Explored the precision–recall tradeoff by adjusting classification thresholds
- Identified an F1-optimal threshold and compared it to the default threshold (0.5)
- Implemented a capacity-constrained threshold selection (maximum 500 flagged transactions)

## Key Findings
The analysis shows that accuracy is highly misleading in imbalanced datasets, as a naive model can achieve over 99% accuracy while failing to detect any fraud. Logistic regression demonstrates strong discriminative ability, with a high ROC-AUC and a more informative PR-AUC for the fraud class. As the classification threshold decreases, Recall improves while Precision declines, illustrating the fundamental tradeoff in fraud detection. The F1-optimal threshold differs from the default 0.5, indicating that model performance can be significantly improved through threshold tuning. Under operational constraints, selecting a threshold based on investigation capacity provides a more realistic and business-relevant decision framework than relying solely on statistical metrics.
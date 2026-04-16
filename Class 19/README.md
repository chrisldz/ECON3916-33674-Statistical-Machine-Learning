# Tree-Based Models — Random Forests

## Objective
This project compares different predictive models on the California Housing dataset to understand how model complexity affects performance and interpretability.

## Methodology
- Trained a Decision Tree, Ridge Regression, and Random Forest on the same dataset  
- Tuned Random Forest hyperparameters using GridSearchCV (n_estimators, max_depth, max_features)  
- Evaluated models using RMSE and R² on both training and test sets  
- Compared feature importance using Mean Decrease in Impurity (MDI) and permutation importance  
- Built a binary classification model to predict high-value houses and evaluated performance using AUC  
- Developed an interactive dashboard using Plotly and ipywidgets to visualize model behavior under different hyperparameters  

## Key Findings
The Random Forest achieved a Test R² of approximately 0.81, which is significantly higher than Ridge Regression (around 0.58). This suggests that the relationship between housing features and prices is non-linear, and ensemble methods are better at capturing these patterns. Hyperparameter tuning slightly improved performance, but the overall gain was modest.

Feature importance analysis shows that median income (MedInc) is the most important predictor. However, this reflects predictive power rather than causality. In the classification task, Random Forest also outperformed Logistic Regression in AUC, although the difference was relatively small.

Overall, Random Forest provides the best predictive performance, while simpler models like Ridge Regression offer better interpretability.
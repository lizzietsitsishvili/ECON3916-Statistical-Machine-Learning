Tree-Based Models — Random Forests
Objective

Evaluate and compare the predictive performance of linear and non-linear models, using Random Forests to capture complex relationships in housing price data while applying modern model evaluation and interpretability techniques.

Methodology
Used the California Housing dataset (20,640 observations, 8 features) as a consistent benchmark dataset
Trained and compared three models: Decision Tree, Ridge Regression, and Random Forest
Evaluated model performance using RMSE and R² on both training and test sets
Tuned Random Forest hyperparameters using GridSearchCV (n_estimators, max_depth, max_features) to optimize predictive performance
Extracted feature importance using both Mean Decrease in Impurity (MDI) and permutation importance to compare training-based vs out-of-sample relevance
Extended the analysis to classification by predicting high-value homes and evaluating performance using AUC
Built an interactive dashboard using Plotly and ipywidgets to visualize how model performance and feature importance change with hyperparameters
Key Findings
Random Forest significantly outperformed Ridge Regression (Test R² ≈ 0.805 vs 0.576), indicating strong non-linear relationships in housing price determinants
A single Decision Tree exhibited severe overfitting (Train R² = 1.000), highlighting high variance and poor generalization
Random Forest reduced variance while preserving flexibility, achieving the best balance on the bias-variance tradeoff
MDI and permutation importance agreed on key drivers (e.g., median income), but diverged for high-cardinality features such as latitude and longitude
Feature importance reflects predictive relevance, not causal impact — reinforcing the distinction between correlation and causation
Hyperparameter tuning provided incremental improvements, with diminishing returns as the number of trees increased
The interactive dashboard revealed how increasing model complexity improves performance up to a point, after which gains plateau

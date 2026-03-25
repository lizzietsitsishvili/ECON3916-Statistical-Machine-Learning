Comparing Model Complexity: Kitchen-Sink vs. Parsimonious Specification
Objective

This exercise evaluates the predictive performance of a fully saturated “kitchen-sink” regression model against a more parsimonious model using only the most informative predictors. The goal is to understand whether adding more features improves generalization or introduces unnecessary complexity.

Methodology

Two models were constructed and evaluated using 5-fold cross-validation:

Kitchen-Sink Model:
Includes all available numeric features in the dataset. This specification minimizes bias by incorporating the full information set but risks overfitting due to increased model complexity.
Simple Model (Top 5 Features):
Restricts the model to the five predictors most strongly correlated with housing prices. These features were selected based on the absolute value of their correlation with the target variable, ensuring that both positive and negative relationships were considered.

To ensure comparability, both models were estimated using linear regression with standardized inputs. Performance was evaluated using Root Mean Squared Error (RMSE) on out-of-sample folds.

Results

The kitchen-sink model achieved a lower average RMSE, indicating stronger predictive performance on unseen data. However, it exhibited greater variability across folds, suggesting sensitivity to the specific training sample.

In contrast, the simpler model produced slightly higher RMSE but demonstrated more consistent performance across folds, indicating greater stability.

Interpretation

This comparison highlights the bias-variance tradeoff:

The kitchen-sink model reduces bias by capturing more relationships in the data but increases variance, making it more sensitive to noise.
The simple model introduces more bias by excluding potentially relevant variables but benefits from lower variance and improved robustness.

While the kitchen-sink model provides better raw predictive accuracy in this case, the marginal gain may not justify the additional complexity, especially if interpretability and stability are priorities.

Key Insight

More features do not always lead to better generalization. A carefully selected subset of predictors can achieve comparable performance while reducing the risk of overfitting—reinforcing the importance of model selection and parsimony in empirical analysis.

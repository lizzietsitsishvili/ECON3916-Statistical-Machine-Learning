Fraud Detection Model Evaluation — Metrics that Matter
Objective

Evaluate the performance of a fraud detection model beyond accuracy by applying advanced classification metrics and threshold optimization techniques to a highly imbalanced real-world dataset.

Methodology
Analyzed a severely imbalanced dataset (0.172% fraud rate) from the Kaggle Credit Card Fraud Detection dataset
Trained a logistic regression classifier to predict fraudulent transactions
Constructed and interpreted confusion matrices across multiple classification thresholds
Computed key evaluation metrics: Precision, Recall, F1-Score, ROC-AUC, and PR-AUC
Visualized model performance using ROC and Precision-Recall curves
Conducted threshold analysis to understand trade-offs between false positives and false negatives
Identified the F1-optimal threshold and compared it to the default 0.5 cutoff
Incorporated a real-world operational constraint (maximum of 500 daily investigations) to determine a business-relevant decision threshold
Key Findings
Demonstrated the accuracy paradox, where a naive model achieved 99.83% accuracy while failing to detect any fraudulent transactions
Showed that accuracy is a misleading metric in imbalanced classification problems, particularly in fraud detection
Logistic regression achieved strong ROC-AUC and meaningful PR-AUC, indicating effective ranking of fraud risk despite class imbalance
Identified that the optimal decision threshold differs significantly from the default 0.5, improving balance between precision and recall
Established that model evaluation must align with operational constraints, as the optimal statistical threshold may not be feasible in practice
Highlighted the importance of Precision-Recall analysis as a more informative metric than ROC in rare-event settings

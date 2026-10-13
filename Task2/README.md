# Task 03: Decision Tree Classifier on the Bank Marketing Dataset

Built and tuned a decision tree classifier to predict whether a bank client will subscribe to a term deposit, using Python, pandas, scikit-learn, matplotlib and seaborn.

- **Source:** UCI Machine Learning Repository, Bank Marketing (https://archive.ics.uci.edu/dataset/222/bank+marketing), Moro, Rita and Cortez (2014), CC BY 4.0
- **Files:** `Task3.ipynb`, `charts/` (5 charts), `bank-full.csv`

## Approach
- 45,211 clients, 16 features, no missing values; only 11.7% subscribed (imbalanced classes)
- Removed `duration` to avoid data leakage (call length is only known after the outcome)
- One-hot encoded categorical columns; stratified 80/20 train/test split
- An unrestricted tree overfit (100% train accuracy, ROC AUC 0.61 on test)
- Tuned `max_depth` and `min_samples_leaf` with 5-fold GridSearchCV and balanced class weights

## Results (test set)
- ROC AUC 0.78, recall 60%, precision 33%, accuracy 81%
- Finds 632 of the 1,058 clients who subscribed
- Top drivers: previous campaign success, contact type, day of contact, housing loan, balance
- With `duration` included, ROC AUC rises to 0.90, which shows why it must be excluded
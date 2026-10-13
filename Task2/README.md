# Task 02: Data Cleaning and EDA on the Titanic Dataset

Cleaned the Titanic dataset and explored the relationships between variables to find patterns in passenger survival, using Python, pandas, matplotlib and seaborn.

- **Source:** Kaggle, Titanic: Machine Learning from Disaster (https://www.kaggle.com/c/titanic/data)
- **Files:** `Task2.ipynb`, `charts/` (9 charts), `train.csv`

## Cleaning
- Age (177 missing): filled with the median age of each class and sex group
- Embarked (2 missing): filled with the most common port (S)
- Cabin (77% missing): converted to a `HasCabin` flag and dropped the original column
- No duplicate rows; high fares kept as genuine first-class tickets

## Key findings
- Overall survival was 38.4%
- 74.2% of women survived versus 18.9% of men
- Survival fell by class: 63.0% (1st), 47.3% (2nd), 24.2% (3rd)
- Children had the best survival rate (58%), seniors the worst (23%)
- Passengers with family (2 to 4 members) survived more than those alone
- Higher fares and recorded cabins went with higher survival, linked to class

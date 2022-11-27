## Multivariate Imputation by Chained Equation (MICE Algorithm)

MICE Imputation is a technique to impute a missing value considering multiple feature columns. It is also called iterative imputer. It is a very popular method of filling the NaN values.

### Assumptions

- Data is missing at random i.e we can use other columns to fill missing values

### Steps:

lets consider there are 3 features and 5 rows. feature 1 has missing value at its second row, feature 2 has missing value at its 4th row and feature 3 has missing value at 5th row. Now follow the steps below:

1. Iteration -1

- Replace the NaN values with the mean of respective column.

2. Iteration-2

- Now we take each feature column from left and move to right.
- Feature 1, replace the mean with NaN again and then train any ML model with other rows i.e 1 , 3, 4 5 row, making feature 2 and 3 input and feature 1 output and then use row 2 as test set, and predict the value which will fill the NaN.
- Now we do same for feature 2(with same model), note that the missing value of feature 1 is filled with the prediction of ML model.
- Same for feature 3.

**Now we subtract Iteration-2 - Iteration-1**

**We repeat the process until the difference is completely zero/ we can make certain limit.**

### Advantage

- Accurate

### Disadvantage

- Slower
- store training set in server.
- requires more memory

### Note

- Same model will be used to predict NA in all variables
- Can't use classification for binary variables and regression for continuous variables

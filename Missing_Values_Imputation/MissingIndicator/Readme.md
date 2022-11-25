## Missing Indicator

When the data are not missing at random, it is a good idea to replace the missing values with mean/median/mode along with providing a flag that indicates the missing value. i.e., prioritizes the missing values. A missing indicator is a binary variable that indicates whether the data was missing (1) or not (0).

### For which variables can I add a missing indicator?

- We can add a missing indicator to both numerical and categorical variables.

#### Note

Adding a missing indicator is never used alone. On the contrary, it is always used together with another imputation technique, which can be mean / median imputation for numerical variables, or frequent category imputation for categorical variables. For both categorical and numerical variables, we can combine random sample imputation with the addition of a missing indicator.

#### Some commonly used combinations are

- Mean/median imputation + missing indicator (Numerical variables)
- Frequent category imputation + missing indicator (categorical variables)
- Random sample imputation + missing indicator (numerical and categorical)

### Assumptions

- This technique assumes that the data are not missing at random.

- This technique assumes that, missing data is predictive.

### Advantages

- Easy to understand and implement.
- Captures the importance of missing data.

### Disadvantage

- Creates additional features which may lead to "Curse of Dimensionality" problem

  Adding a missing indicator will increase the number of variables in the dataset. So if the dataset contains 10 features, and all of them have missing values, after adding a missing indicator, we will have a dataset with 20 features: the original 10 features plus an additional 10 binary features, which indicate for each of the original variables whether they were missing or not. This may not be a problem in datasets with tens to a few hundred variables, but if our original dataset contains thousands of variables, by creating an additional variable to indicate NA, we will end up with very big datasets.

- Data tends to be missing across multiple variables, which often leads to many of the missing indicators being similar to or even identical to each other.

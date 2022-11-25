## Imputing missing values with Mean/Median/Mode

Columns in the dataset which are having numeric continuous values can be replaced with the mean, median, or mode of remaining values in the column. This method can prevent the loss of data compared to the earlier method. Replacing the above two approximations (mean, median) is a statistical approach to handle the missing values.

Mean imputation is used if the data's have **Gaussian Distribution** and Median imputation is used if the data's have **Skewed Distribution**.

Mode imputation is mostly used with categorical variables and least used with continous features.

### Things to consider before using Mean/Median/Mode

- This method is used with an assumption that the data are missing completely at random.
- This method should be used when there is no more than 5% of the variables contains missing data.

### Advantages:

- Prevent data loss which results in deletion of rows or columns
- Works well with a small dataset and is easy to implement.
- Easy to implement and is robust to outlier(median).

### Disadvantages:

- Change or distortion in the original variance
- Can cause data leakage
- Do not factor the covariance between features.

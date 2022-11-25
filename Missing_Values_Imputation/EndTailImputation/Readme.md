## End of Tail Imputation

End of tail imputation is similar to arbitrary value imputation,
but in this technique we select the arbitrary values from the end of the variable distribution.

This method is mostly used in financial companies. When capturing the financial history of the customers, the missing data is replaced by a value at the end of distribution to capture the importance of "Missingness".

### How do we select the value at the end?

- If the variable is normally distributed, we can use the mean plus or minus 3 times the standard deviation
- If the variable is skewed, we can use the IQR proximity rule

### Which variables can I impute with an arbitrary value?

This method is generally suitable for numerical variables.

### Assumptions:

- This method assumes that the data are not missing at random.

If the value is not missing at random, we don’t want to replace it for the mean/median and therefore make that observation look like the majority of our observations. Instead, we want to flag that observation as different, and therefore we assign a value that is at the tail of the distribution, where observations are rarely represented in the population.

### Advantages:

- Easy to understand and implement
- Fast way of obtaining complete datasets
- Can be integrated into production (during model deployment)
- Captures the importance of “missingness” if there is one

### Disadvantages:

- Distortion of the original variable distribution
- Distortion of the original variance
- Distortion of the covariance with the remaining variables of the dataset
- This technique may mask true outliers in the distribution

## Arbitrary Value Imputation

Arbitrary value imputation is the process of replacing all occurrences of missing values (NaN) within a variable by an arbitrary value.

The most commonly used arbitrary values are 0, 999, -999 (or other combinations of 9s) or -1 (if the distribution is positive).

### Which variables can I impute with an arbitrary value?

- Both categorical and numerical variables can be imputed by arbitrary values.

- For categorical variables, this is the equivalent of replacing all instances of NaN by an additional label called ‘Missing’, which is a very common practice.

### Which arbitrary value to use?

Ideally we will look for the values that are at the end of distribution.

### Assumptions:

- Data is not missing at random(MAR).

If this is the case, we want to flag the missing values with a different (arbitrary) value, instead of replacing those occurrences with the mean or the median, which represent the most common value.

### Advantages:

- Easy to understand and implement.
- Fast way of obtaining complete datasets.
- Can be integrated into production (during model deployment).
- Captures the importance of “missingness” if there is one.

### Limitations:

- Distortion of the original variable distribution.
- Distortion of the original variance.
- Distortion of the covariance with the remaining variables of the dataset
  - It may mask or create outliers.
  - We need to be careful while choosing the arbitrary value and ensure that the value choosen is not too similar to the mean or median (or any other common value of the variable distribution).

### When to use arbitrary value imputation:

This technique of replacing the NaN values should be used when the data is missing not at random. In situations like this, instead of replacing the NaN values with median/mean/mode, we would like to replace it with some values that flag the fact that the observation is missing.

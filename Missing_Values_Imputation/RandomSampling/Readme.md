## Random Sample Imputation:

In Random Sample Imputation, we take random observations from the dataset and use them to replace the NaN values.

Random sampling consists of taking random observations from the pool of available data and using them to replace the NA. In random sample imputation, we take as many random observations as missing values exist in the variable.

Random Sampling can be applied to both numerical and categorical features.

Random Sampling method assumes that the data are missing completely at random. In this scenario, it makes sense to substitute the missing values with values extracted at random from the original distribution.

### We should particulary use this method when:

- Data is missing completely at random
- No more than 5% of the variables contain missing data.
- Well suited for linear models as it does not distort the distribution, regardless of the percenage of NA

### Some important thing to remember before using random sampling

While using random sampling to replace the NaN values, the randomness of replacing the data needs to be controlled, so that individuals in the same situation end up with the same scores and, therefore, with the same solutions offered. This can be done by appropriately setting seeds during the random extraction of values.

### Advantages:

- The variable distribution remains unchanged.

### Disadvantages:

- Random sampling will not work in every scenarios, we need to do some check before using it.
- The relationship of imputed variables with other variables may be affected if there are a lot of NA
- It is computationally expensive than method 1 and 2
- The estimations of covariance and correlations with other variables in the dataset may be distorted, especially if there are many missing observations.

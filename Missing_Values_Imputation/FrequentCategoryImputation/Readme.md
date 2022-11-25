## Frequent Category Imputation / Mode Imputation

Frequent category imputation/ Mode imputation is the process of replacing all occurances of missing values (NaN) within a variable with the mode value, i.e., the most frequent value or most frequent category.

### Which variables can I impute with the most frequent category?

This technique can be used for both numerical and categorical features. But, in practice, we only use this method on categorical features. It's because, mean/median tend to better represent the population's average value.

### Assumptions

- This technique assumes that the data is missing completely at random.
- No more than 5% of the variable contains missing data.

If data is missing at random, the value for the missing observation will most likely look like the majority of the observations, that is, the most frequent category of the variable.

### Advantage

- It is easy to understand and implement.
- It is the fast way of obtaining complete datasets.
- It can be integrated in production (during model deployment).

### Disadvantage

- It distorts the relation of the most frequent label with other variables within the dataset.
- It May lead to an over-representation of the most frequent label if there is a big number of NA.
- It may create bias due to over-representation of the most frequent label.

### When to use mode / most frequent category imputation?

- When the data is missing completely at random.
- When the percentage of variable containing missing data is not more than 5%.

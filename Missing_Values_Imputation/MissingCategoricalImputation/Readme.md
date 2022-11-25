## Missing Categorical Imputation

It is one of the methods of handling the missing values for categorical variables. In this method the missing data's are treated as an additional new category of the variable. For instance, all the missing values are grouped under a newly created label named 'Missing' or so.

This technique is mostly used to handle the categorical values.

This technique is similar to the Arbitrary Value Imputation used for numerical features.

The beauty of this technique resides in the fact that it doesnot assume anything about the missing data. i.e, where the data is missing at random, or data is not missing at random.

This method is very well suited when the number of missing data points is high.

# Advantages

- Easy to understand and implement.
- Fast way of obtaining complete datasets.
- Can be integrated into production (during model deployment)
- Highlights missing data
- No assumption made on the data

### Disadvantages

- If the number of NA is small, creating an additional category may introduce noise
  For categorical variables, this is the method of choice, as it treats missing values as a separate category, without making any assumptions about the variable or the reasons why data could be missing.

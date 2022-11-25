## One Hot Encoding of Frequent Categories

One-hot encoding is one of the most common encoding methods in machine learning for nominal categorical features. This method spreads the values in a column to multiple flag columns and assigns 0 or 1 to them. These binary values express the relationship between grouped and encoded column. These binary values are also known as dummy variables.

But if we apply one hot encoding to the problem where we have many categorical features and those features in turn have many categories, the size of the feature column will be very huge and we will eventually face the 'Curse of Dimensionality' problem which will inturn reduce the model accuracy.

In order to avoid these complications, we can create dummy variables only for the most frequent categories(10 categories)

This procedure is also called one hot encoding of top categories.

In fact, in the winning solution of the KDD 2009 cup: "Winning the KDD Cup Orange Challenge with Ensemble Selection", the authors limit one hot encoding to the 10 most frequent labels of the variable. This means that they would make one binary variable for each of the 10 most frequent labels only.

### Advantages of OHE of top categories

- Straightforward to implement
- Does not require hrs of variable exploration
- Does not expand massively the feature space
- Suitable for linear models

### Disadvantages

- Does not add any information that may make the variable more predictive
- Does not keep the information of the ignored labels

### NOTE:

1. Often, categorical variables show a few dominating categories while the remaining labels add little information. Therefore, OHE of top categories is a simple and useful technique.
2. The number of top category is a hyperparemeter. We can tweak it to get the best result.

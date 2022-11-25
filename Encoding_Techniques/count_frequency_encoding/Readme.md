## Count or Frequency Encoding

The features having many number of categories are called as the features having high cardinality.

Because of high cardinality, handling the categorical feature with one-hot encoding may lead to the problem of "Curse of Dimensionality".

Count Encoding is one of the many solution to this problem. In this approach, we replace each categories of the categorical features by the count/frequency of their occurance, i.e., the number of times each category appears in the dataset.

i.e., if 10 of our 100 observations show the colour blue, we would replace blue by 10 if doing count encoding, or by 0.1 if replacing by the frequency.

These techniques capture the representation of each label in a dataset, but the encoding may not necessarily be predictive of the outcome. These are however, very popular encoding methods in Kaggle competitions.

Frequency Encoding is a normalized version of count encoding.

The assumption of this technique is that the number observations shown by each variable is somewhat informative of the predictive power of the category.

### Advantages

1. It is very simple to understand and implement
2. It doesn't increase the number of features and prevent from the "Curse of Dimensionality"

### Disadvantages

1. If some of the labels have same count, they will be replaced with the same count value. Due to this we loose some valuable information for the prediction.
2. It adds some arbitrary numbers, and therefore weights to the different labels, that may not be related to their predictive power.

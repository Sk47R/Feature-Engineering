### Count or Frequency Encoding

The features having many number of categories are called as the features having high cardinality.

Because of high cardinality, handling the categorical feature with one-hot encoding may lead to the problem of "Curse of Dimensionality".

Count Encoding is one of the many solution to this problem. In this approach, we replace each categories of the categorical features by the count/frequency of their occurance, i.e., the number of times each category appears in the dataset.

Frequency Encoding is a normalized version of count encoding.

**To see how the code works, check the files above**

---

### Advantages

1. It is very simple to understand and implement
2. It doesn't increase the number of features and prevent from the "Curse of Dimensionality"

### Disadvantages

1. If some of the labels have same count, they will be replaced with the same count value. Due to this we loose some valuable information for the prediction.
2. It adds some arbitrary numbers, and therefore weights to the different labels, that may not be related to their predictive power.

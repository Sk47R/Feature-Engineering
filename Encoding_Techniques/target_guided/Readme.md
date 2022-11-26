## Target guided encodings

There are methods that allow us to capture information while pre-processing the labels of categorical variables. These methods include:

- Ordering the labels according to the target
- Replacing labels by the target mean (mean encoding / target encoding)
- Replacing the labels by the probability ratio of the target being 1 or 0
- Weight of evidence.

All these above methods have something in common. That is, the encodings are guided by the target, and they create a monotonic relationship between the variable and the target.

### Monotonicity

A monotonic relationship is a relationship that does one of the following:

- as the value of one variable increases, so does the value of the other variable, or
- as the value of one variable increases, the value of the other variable decreases.

In this case, as the value of the independent variable (predictor) increases, so does the target, or conversely, as the value of the variable increases, the target value decreases.

### Advantages

- Capture information within the category, therefore creating more predictive features.
- Create a monotonic relationship between the variable and the target, therefore suitable for linear models.
- Does not increase the number of feature columns.

### Disadvantages

- Prone to cause over-fitting
- Difficult to cross-validate with current libraries

### Note

This method can be also used on numerical variables, after discretisation. This creates a monotonic relationship between the numerical variable and the target, and therefore improves the performance of linear models.

---

### Ordered Integer Encoding

Ordering the categories according to the target means assigning a number to the category from 1 to k, where k is the number of distinct categories in the variable, but this numbering is informed by the mean of the target for each category.

For example, we have the variable city with values London, Manchester and Bristol; if the default rate is 30% in London, 20% in Bristol and 10% in Manchester, then we replace London by 1, Bristol by 2 and Manchester by 3.

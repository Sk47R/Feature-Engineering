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

## This method can be also used on numerical variables, after discretisation. This creates a monotonic relationship between the numerical variable and the target, and therefore improves the performance of linear models.

## Mean Encoding

Mean Encoding is the technique in which we replace te category values by the mean/ average value for that category.

For Example: If we have 4 categories in a categorical column, 'A', 'B','C','D' . Then we calculate the mean of the output for each categories. Finally we replace the categories with that mean values. If output mean for category A is 0.6 we replace A by 0.6, and so on.

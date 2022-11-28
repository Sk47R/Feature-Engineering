## Gaussian Transformation

Machine learning models like linear and logistic regression assumes that the variables/ feature are normally distributed. However, very often the variables are not normally distributed i.e. they are skewed. Transforming the skewed data to normal distribution often boosts the performance of the machine learning algorithm.

If a variable is not normally distributed, it is often possible to find a mathematical transformation to normalise its distribution.

### Variable Transformation Methods

- Some of the variable transformation methods are listed below:

1. Logarithmic transformation - np.log(X)
2. Reciprocal transformation - 1 / X
3. Square root transformation - X\*\*(1/2)
4. Exponential transformation (more general, you can use any exponent)
5. Box-Cox transformation
6. Yeo-Johnson transformation

### Box-Cox Transformation

A Box Cox transformation is a transformation of non-normal dependent variables into a normal shape. Normality is an important assumption for many statistical techniques; if your data isn’t normal, applying a Box-Cox means that you are able to run a broader number of tests.

The Box-Cox transformation is an adaptation of the exponential transformation, scanning through various exponents, and it already represents the untransformed variable, as well as the log transformed, reciprocal, square and cube root transformed, as the lambda varies across the range of -5 to 5 . So by doing Box-Cox transformation, in a way, we are evaluating all the other transformations and choosing the best one. Box-Cox can only be applied to positive variables.

Yeo-Johnson is a modification of the Box-Cox transformation so that it can be applied as well to non-positive variables

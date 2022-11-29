## MaxAbsScaling

Maximum absolute scaling scales the data to its absolute maximum value:

Formula:

X_scaled = X / abs(X.max)

The result of the above transformation is a distribution which values vary within the range of -1 to 1. But the mean is not centered at zero and the standard deviation varies across variables.

Scikit-learn suggests that this transformer is meant for data that is centered at zero, and for sparse data.

To sum up, MaxAbsScaling:

- does not center the mean at 0 (but it might be a good idea to center it with another method)
- variance varies across variables
- may not preserve the shape of the original distribution
- sensitive outliers

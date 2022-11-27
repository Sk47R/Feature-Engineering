## KNN Imputer

KNN Impute is a technique to impute a missing value considering multiple feature columns. It works on KNN algorithm.

Say we have 3 features 'A', 'B', 'C' and it has 5 rows. Each row is represented by a 3-D point (x, y, z), where x represents 'A', y represents 'B' and z represents 'C'. Let's consider the x coordinate of row1 is missing and other all values are present. To find the x coodinate what we do is, we calculate the euclidean distance between row1 and other 5 rows. Then we find the row having shortest distance with row1 and then fill the missing x coordinate of row1 with the x coordinate of row that has the shortest distance.

In KNN we consider multiple neighbor, i.e multiple shortest distance , so we have to take the arithmetic mean of all the values.

### Steps for KNN-Imputer:

- Find the k nearest neighbor.
- Then find the value to be filled by taking the mean of all the neighbor.

Here to find the distance we don't use simple euclidean distance as there might be other nan values in any other row or the same row. So we use nan_euclidean distance.

### NaN Euclidean Distance

It is used to calculate the euclidean distance in presence of NaN values.

It computes the euclidean distance between each pair of samples in X and Y, where Y=X is assumed if Y=None. When calculating the distance between a pair of samples, this formulation ignores feature coordinates with a missing value in either sample and scales up the weight of the remaining coordinates:

Formula:

dist(x,y) = sqrt(weight \* sq. distance from present coordinates) where, weight = Total no. of coordinates / no. of present coordinates

For example, the distance between [3, na, na, 6] and [1, na, 4, 5] is:

$$ x = {sqrt{(4/2)\*((3-2)^2 + (6-5)^2) }} $$

As we can see the onces wit nan is ignored and weight is applied.

### Advantages

- It is more accurate.
- Best for small dataset than mean/median/mode imputation.

### Disadvantage

- Computational time and complexity increases.
- In production deployment, we need to add the entire training set to server. Because to calculate te missing value in new datas we need to use all the data's of training set.

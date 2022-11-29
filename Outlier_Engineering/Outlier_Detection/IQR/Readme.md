## Inter Quartile Range(IQR)

IQR is a technique that is used to detect outlier present in the dataset. It assumes that the data points that lie 1.5 times of IQR above Q3 and below Q1 are outliers and others are normal datas.

where

Q1 represents the 1st quartile/25th percentile of the data.

Q2 represents the 2nd quartile/median/50th percentile of the data.

Q3 represents the 3rd quartile/75th percentile of the data.

(Q1–1.5IQR) represent the smallest value in the data set and (Q3+1.5IQR) represent the largest value in the data set

## Steps Involved:

1. Sort the dataset in ascending order
2. calculate the 1st and 3rd quartiles(Q1, Q3)
3. compute IQR=Q3-Q1
4. compute lower bound = (Q1–1.5*IQR), upper bound = (Q3+1.5*IQR)
5. loop through the values of the dataset and check for those who fall below the lower bound and above the upper bound and mark them as outliers

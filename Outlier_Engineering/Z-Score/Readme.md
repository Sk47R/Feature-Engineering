## Z-Score

This method assumes that the variable has a Gaussian distribution. In this technique we calculate the Z score value. Then we check whether that value is less than the threshold (i.e. we assusme that the data falling inside 3 Standard Deviation as normal data and data falling away are outliers).

If Z-score < threshold, it is not an outlier, else it is.

Formula for Z score = (Observation — Mean)/Standard Deviation

z = (X — μ) / σ

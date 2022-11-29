## Outlier

Outliers are those data points which differs significantly from other observations present in given dataset. It can occur because of variability in measurement and due to misinterpretation in filling data points.

Statistics such as the mean and variance are very susceptible to outliers. In addition, some Machine Learning models are sensitive to outliers which may decrease their performance. Thus, depending on which algorithm we wish to train, we often remove outliers from our variables.

## How outliers are introduced in the datasets?

Most common causes of outliers on a data set:

1. Data Entry Errors: Human errors such as errors caused during data collection, recording, or entry can cause outliers in data.
2. Measurement Error (instrument errors): It is the most common source of outliers. This is caused when the measurement instrument used turns out to be faulty.
3. Experimental errors (data extraction or experiment planning/executing errors)
4. Intentional (dummy outliers made to test detection methods)
5. Data processing errors (data manipulation or data set unintended mutations)
6. Sampling errors (extracting or mixing data from wrong or various sources)
7. Natural Outlier (not an error, novelties in data): When an outlier is not artificial (due to error), it is a natural outlier. Most of real world data belong to this category.

## Should outliers be removed?

Depending on the context of the problem, outliers either deserve special attention or should be ignored. Take the example of revenue forecasting: if unusual spikes of revenue are observed, it's probably a good idea to pay extra attention to them and figure out what caused the spike. In the same way, an unusual transaction on a credit card might be a sign of fraudulent activity, which is what the credit card issuer wants to prevent. So, in instances like these, it is useful to look for and investigate further the outlier values.

If outliers are, however, introduced by mechanical or measurement error, it is a good idea to remove these outliers before training the model. Why? because some algorithms are sensitive to outliers.

## Machine learning models and outliers

Some machine learning models are sensitive to outliers. For instance, AdaBoost may treat outliers as "hard" cases and put tremendous weights on them, thus producing a model with poor generalisation.

Linear models, in particular linear regression, can also be sensitive to outliers.

Decision trees-based models are robust to outliers. Decision trees make decisions by asking if variable x is >= than a certain value, and therefore the outlier will fall on each side of the equation, but it will be treated similarly to non-outlier values.

A research article suggests that neural networks could also be sensitive to outliers, provided the number of outliers is high and the deviation is also high. If the number of outliers is high (> 15% as suggested in the article), then they are no longer outliers, but rather a fair representation of that variable.

## How to detect Outliers?

Different technique of detecting outliers are:

1. Hypothesis Testing

2. Z-score method

3. Robust Z-score

4. I.Q.R method

5. Winsorization method (Percentile Capping)

6. DBSCAN Clustering

7. Isolation Forest

8. Linear Regression Models (PCA, LMS)

9. Standard Deviation

10. Percentile

11. Visualizing the data

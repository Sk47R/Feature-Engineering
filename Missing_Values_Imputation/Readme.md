## Missing Values

Missing values is defined as the values or data that is not stored (or not present) for some variable/s in the given dataset.

It is one of the most common problems we encounter when we try to prepare our data for machine learning. The reason for the missing values might be human errors, interruptions in the data flow, privacy concerns, and so on. Whatever is the reason, missing values affect the performance of the machine learning models.

Some machine learning platforms automatically drop the rows which include missing values in the model training phase and it decreases the model performance because of the reduced training size. On the other hand, most of the algorithms do not accept datasets with missing values and gives an error.

## Why Is Data Missing From The Dataset?

There may be various reason for having missing data's in a dataset. In order to handle the missing data, it is very important to understand why the data's could be missing.

Some of the reasons for it are:

- Past data of the database from which we extract the data might get corrupted due to improper maintenance.
- Observations are not recorded for certain fields due to some reasons. There might be a failure in recording the values due to human error.
- The user has not provided the values intentionally.
- Due to privacy concern in some of the survey's.

## Types of Missing Data

It is the duty of Domain Expert to tell the types of missing data to the data scientist so that he/she can solve the problem of missing value sensibly. There are basically three types of missing values

### 1.Missing Completely at Random (MCAR):

A data is said to be missing completely at random if the probability of being missing is the same for all the observations. When data is MCAR, there is absolutely no relationship between the data missing and any other values, observed or missing, within the dataset. In other words, those missing data points are a random subset of the data. There is nothing systematic going on that makes some data more likely to be missing than other and they donot follow any discernable pattern.

These values are most clearly identified when you cannot predict the missing value from the remaining know variables. The fact that it is missing is independent of the remaining variables.

In the case of MCAR, the data could be missing due to human error, some system/equipment failure, loss of sample, or some unsatisfactory technicalities while recording the values.

For example:

- In titanic data sets, there are three columns(features) having missing values, Age, Cabin and Embarked. The reason for the feature Embarked to have some missing value is totally independent to the reason for the features Age and Cabin having some missing values.
- Some chemical students may have missing laboratory values because a batch of lab samples was processed improperly. In these instances, the missing data reduce the analyzable population of the study and consequently, the statistical power, but do not introduce bias: when data are MCAR, the data which remain can be considered a simple random sample of the full data set of interest.

### 2.Missing at Random (MAR):

If the reason for missing values of certain features can be explained by the variables on which you have complete information as there is some relationship between the missing data and other values/data, then those data's are said to be missing at random.

In this case of missing data, the data's are not missing for all the observations. It is missing only within sub-samples of the data and there is some pattern in the missing values.

For example:

- imagine a sensor that misses a particular minute’s measurement but captures that data the minute before and the minute following. The missing value can roughly be interpolated from the remaining values to a reasonable degree of accuracy.
- In survey, we may find that all the people have answered their ‘Gender’ but ‘Age’ values are mostly missing for people who have answered their ‘Gender’ as ‘female’. (The reason being most of the females don’t want to reveal their age).So, the probability of data being missing depends only on the observed data. In this case, the variables ‘Gender’ and ‘Age’ are related and the reason for missing values of the ‘Age’ variable can be explained by the ‘Gender’ variable but you can not predict the missing value itself.

### 3. Missing Data Not at Random (MNAR):

If there is some structure/pattern in missing data and other observed data can not explain it, these are said to be missing data not at random.

When the data are missing systematically related to the unobserved data, i.e., the data is NULL/NAN is related to some events or factors which are not measured by the researcher, then the data is said to be missing data not at random. It means that there is some relationship between the missing data and any other values, observed or missing, within the dataset but still the values can not effectively be inferred or predicted..

For example:

- In a survey people avoiding/ skipping question like, for example, people in a certain age/income bracket refuse to answer how many vehicles or houses they own. The mechanism here may be apparent, but inferring the actual value of the missing data is difficult to predict accurately.

- In titanic dataset the missing values in feature Age and feature Cabin may be related, but the solution for that is not possible to get.

## Is Handling Missing Values Necessery?

Yes, handling missing values is absolutely necessery and is one of the preliminary step in data analysis.

- Many machine learning algorithms fail if the dataset contains missing values. However, algorithms like K-nearest and Naive Bayes support data with missing values.
- You may end up building a biased machine learning model which will lead to incorrect results if the missing values are not handled properly.
- Missing data can lead to a lack of precision in the statistical analysis.
- Missing data will lead to low accuracy of the model.

## Ways To Handle Missing Values!

### 1. Deleting row/columns with missing values

The most simple solution to the missing values is to drop the rows or the entire column. There is no any optimial threshold value for dropping but we can consider >60% or typically 70% as the threshold. i.e, if a column contains more than 70% missing value, we simply drop it.

#### Advantanges:

- We can built a robust model without missing values.

#### Disadvantage:

- Loss of a lot of information.
- Works poorly if the percentage of missing values is excessive in comparison to the complete dataset.

### 2. Imputation

Imputation is the process of replacing missing data with statistical estimates of the missing values. The goal of any imputation technique is to produce a complete dataset that can be used to train machine learning models.

#### 2.a Imputing missing values with Mean/Median/Mode

Columns in the dataset which are having numeric continuous values can be replaced with the mean, median, or mode of remaining values in the column. This method can prevent the loss of data compared to the earlier method. Replacing the above two approximations (mean, median) is a statistical approach to handle the missing values.

Mean imputation is used if the data's have **Gaussian Distribution** and Median imputation is used if the data's have **Skewed Distribution**.

Mode imputation is mostly used with categorical variables and least used with continous features.

##### Things to consider before using Mean/Median/Mode

- This method is used with an assumption that the data are missing completely at random.
- This method should be used when there is no more than 5% of the variables contains missing data.

#### Advantages:

- Prevent data loss which results in deletion of rows or columns
- Works well with a small dataset and is easy to implement.
- Easy to implement and is robust to outlier(median).

#### Disadvantages:

- Change or distortion in the original variance
- Can cause data leakage
- Do not factor the covariance between features.

#### 2.b Categorical Imputation

When missing values is from categorical columns (string or numerical) then the missing values can be replaced with the most frequent category. But if the calues in the columns are distributed uniformly then there is not a dominant value for the replacement. In this case, inputing a new category like "MISSING" might be more sensible.

#### Advantages:

- Prevent data loss which results in deletion of rows or columns
- Works well with a small dataset and is easy to implement.
- Negates the loss of data by adding a unique category

#### Disadvantages:

- Addition of new features to the model while encoding, which may result in poor performance

#### 2.c Random Sample Imputation:

In Random Sample Imputation, we take random observations from the dataset and use them to replace the NaN values.

Random sampling consists of taking random observations from the pool of available data and using them to replace the NA. In random sample imputation, we take as many random observations as missing values exist in the variable.

Random Sampling can be applied to both numerical and categorical features.

Random Sampling method assumes that the data are missing completely at random. In this scenario, it makes sense to substitute the missing values with values extracted at random from the original distribution.

##### We should particulary use this method when:

- Data is missing completely at random
- No more than 5% of the variables contain missing data.
- Well suited for linear models as it does not distort the distribution, regardless of the percenage of NA

##### Some important thing to remember before using random sampling

While using random sampling to replace the NaN values, the randomness of replacing the data needs to be controlled, so that individuals in the same situation end up with the same scores and, therefore, with the same solutions offered. This can be done by appropriately setting seeds during the random extraction of values.

#### Advantages:

- The variable distribution remains unchanged.

#### Disadvantages:

- Random sampling will not work in every scenarios, we need to do some check before using it.
- The relationship of imputed variables with other variables may be affected if there are a lot of NA
- It is computationally expensive than method 1 and 2
  - The estimations of covariance and correlations with other variables in the dataset may be distorted, especially if there are many missing observations.

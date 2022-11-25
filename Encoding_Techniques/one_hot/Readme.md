## One hot Encoding

One-hot encoding is one of the most common encoding methods in machine learning for nominal categorical features. This method spreads the values in a column to multiple flag columns and assigns 0 or 1 to them. These binary values express the relationship between grouped and encoded column. These binary values are also known as dummy variables.

This method changes your nominal categorical data, which is challenging to understand for algorithms, to a numerical format and enables you to group your categorical data without losing any information.

For example

1. For a categorical feature say "Gender", with labels 'male' and 'female', we can assign a boolean value 1 if the person is male and 0 if the person is female, or we can assign a boolean value 1 if the person is female and 0 if the person is male.

2. For the categorical variable "colour" with values 'red', 'blue' and 'green', we can create 3 new feature columns named "red", "blue" and "green". These variables will take the value 1, if the observation is of the respective color or 0 otherwise.

### Encoding into k-1 dummy variables

Instead of encoding the variable 'color' to 3 different features, we can instead represent all the information with only 2 features.

- if the observation is red, it will be captured by the variable "red" (red = 1, blue = 0)
- if the observation is blue, it will be captured by the variable "blue" (red = 0, blue = 1)
- if the observation is green, it will be captured by the combination of "red" and "blue" (red = 0, blue = 0)

We do not need to add a third variable "green" to capture that the observation is green. This is also known as **Dummy Variable Trap**. And by representing N categories with just N-1 column, we overcome this trap.

More generally, a categorical variable should be encoded by creating k-1 binary variables, where k is the number of distinct categories. In the case of gender, k=2 (male / female), therefore we need to create only 1 (k - 1 = 1) binary variable. In the case of colour, which has 3 different categories (k=3), we need to create 2 (k - 1 = 2) binary variables to capture all the information.

One hot encoding into k-1 binary variables takes into account that we can use 1 less dimension and still represent the whole information: if the observation is 0 in all the binary variables, then it must be 1 in the final feature column which is not present.

NOTE: Most machine learning algorithms, consider the entire data set while being fit. Therefore, encoding categorical variables into k - 1 binary variables, is better, as it avoids introducing redundant information.

### Exception for One hot encoding into k dummy variables

There are some occasions when it is better to encode variables into k dummy variables:

- when building tree based algorithms
  - The tree based algorithms, as opposed to the majority of machine learning algorithms, do not evaluate the entire dataset while being trained. They randomly extract a subset of features from the data set at each node for each tree. Therefore, if we want a tree based algorithm to consider all the categories, we need to encode categorical variables into k binary variables.
- when doing feature selection by recursive algorithms
- when interested in determine the importance of each single category

If we are planning to do feature selection by recursive elimination (or addition), or if we want to evaluate the importance of each single category of the categorical variable, then we will also need the entire set of binary variables (k) to let the machine learning model select which ones have the most predictive power.

### Advantages

- Easy to implement and understand
- Does not require time to explore the variables
- Makes no assumption about the distribution or categories of the categorical variable
- Keeps all the information of the categorical variable
- Suitable for linear models

### Disadvantage

- It will increase the number of feature columns. This may lead to problem of "Curse of Dimensionality" when we have many categorical feature to encode.
- Does not add extra information while encoding
- Many dummy variables may be identical, introducing redundant information
- Loss of some information

#### Why called One-hot?

If you have N distinct values in the column, it is enough to map them to N-1 binary columns, because the missing value can be deducted from other columns. If all the columns in our hand are equal to 0, the missing value must be equal to 1. This is the reason why it is called as one-hot encoding. It is also known as dummy variable trap.

#### Nominal data:

It is a type of categorical data that consists of the name variable without any numerical values or Order. For example, in any organization, the name of the different departments like research and development department, human resource department, accounts and billing department, Gender,etc.

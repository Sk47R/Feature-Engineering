### One hot Encoding

One-hot encoding is one of the most common encoding methods in machine learning for nominal categorical features. This method spreads the values in a column to multiple flag columns and assigns 0 or 1 to them. These binary values express the relationship between grouped and encoded column.

This method changes your nominal categorical data, which is challenging to understand for algorithms, to a numerical format and enables you to group your categorical data without losing any information.

#### Why called One-hot?

If you have N distinct values in the column, it is enough to map them to N-1 binary columns, because the missing value can be deducted from other columns. If all the columns in our hand are equal to 0, the missing value must be equal to 1. This is the reason why it is called as one-hot encoding. It is also known as dummy variable trap.

#### Nominal data:

It is a type of categorical data that consists of the name variable without any numerical values or Order. For example, in any organization, the name of the different departments like research and development department, human resource department, accounts and billing department, Gender,etc.

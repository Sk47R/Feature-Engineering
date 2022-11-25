## Integer Encoding

Integer Encoding is a process in which the categories of the categorical features are replaced by digits from 1 to n (or 0 to n-1, depending upon the implementation), where n is the number of distinct categories of the variable.

The numbers are assigned arbitrarily. This encoding method allows for quick benchmarking of machine learning models.

### Advantages

- Easy to understand and implement
- Does not increase the number of feature columns

### Disadvantages

- Does not capture any information about the categories labels
- Not suitable for linear models.

NOTE: Integer encoding is better suited for non-linear methods which are able to navigate through the arbitrarily assigned digits to try and find patterns that relate them to the target.

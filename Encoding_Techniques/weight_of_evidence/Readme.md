## Weight of evidence

Weight of Evidence (WoE) was developed primarily for the credit and financial industries to help build more predictive models to evaluate the risk of loan default. That is, to predict how likely the money lent to a person or institution is to be lost. Thus, Weight of Evidence is a measure of the "strength” of a grouping technique to separate good and bad risk (default).

The weight of evidence tells the predictive power of an independent variable in relation to the dependent variable.

WOE can be calculated as:
WoE = ln(Distribution of Goods/ Distribution of Bads)

where:

- Distribution of Goods: is the percentage of Good in a particular group
- Distribution of Bads: is the percentage of Bad in a particular group
- ln: natural log

- WoE will be 0 if the P(Goods) / P(Bads) = 1, that is, if the outcome is random for that group.
- If P(Bads) > P(Goods) the Woe will be < 1 and,
- WoE will be > 1 if, P(Goods) > P(Bads).

WoE is well suited for Logistic Regression, because the Logit transformation is simply the log of the odds, i.e., ln(P(Goods)/P(Bads)). Therefore, by using WoE-coded predictors in logistic regression, the predictors are all prepared and coded to the same scale, and the parameters in the linear logistic regression equation can be directly compared.

### Steps of Calculating WoE

- For a continuous variable, split data into 10 parts (or lesser depending on the distribution).
- Calculate the number of events and non-events in each group (bin)
- Calculate the % of events and % of non-events in each group.
- Calculate WOE by taking natural log of division of % of non-events and % of events

Note : For a categorical variable, you do not need to split the data (Ignore Step 1 and follow the remaining steps)

![Calculation of WoE](url "https://1.bp.blogspot.com/-eNJ4G_DqhUs/XNRigoIXh2I/AAAAAAAAHiU/8Bt059tLpDoc6DKBUPCOf3ffOW2eOO2DQCLcBGAs/s1600/IV_WOE.png")

Image taken from Listen Data.

### Advantages

- It creates a monotonic relationship between the target and the independent variables.
- It orders the categories on a "logistic" scale which is natural for logistic regression
- The transformed variables can then be compared because they are on the same scale. Therefore, it is possible to determine which one is more predictive.

### Disadvantage

- Prone to cause over-fitting

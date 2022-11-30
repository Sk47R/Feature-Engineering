## Engineering Dates

Date variables are special type of categorical variable. By their own nature, date variables will contain a multitude of different labels, each one corresponding to a specific date and sometimes time. Date variables, when preprocessed properly can highly enrich a dataset. For example, from a date variable we can extract:

- Week of the year
- Month
- Quarter
- Semester
- Year
- Day (number)
- Day of the week
- Is Weekend?
- Time differences in years, months, days, hrs, etc.

Date variables should not be used as categorical variables when building a machine learning model. Not only because they have a multitude of categories, but also because when we actually use the model to score a new observation, this observation will most likely be in the future, an therefore its date label, might be different from the ones contained in the training set and therefore the ones used to train the machine learning algorithm.

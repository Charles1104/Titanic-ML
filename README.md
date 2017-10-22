# Kaggle Competition - Titanic

![alt text](titanic.jpg)

## Short summary

This task requires participants to predict if a Titanic passenger will survive or not to the sank of the Titanic based on some passenger's features.

## Methodology

I started by exploring the dataset in order to get some insights about each features. Some visualizations helped me to notice some interesting patterns like the strong correlation between the class or sex of a passenger with the chance of survival.

After this exploration phase I started to clean the data by changing the non-numerical features into numerical features (needed for machine learning to make sense of the data). Then I dealt with the missing values for each features. For the port of embarkation, I replaced the few missing values with the most frequent port of embarkation; for the age, I grouped the dataframe by class and sex and replaced the misisng values in each subgroups by the median of each subgroup; for the fare, I replaced by the mean value. I also created a new feature "Family size" that gives the number family relatives on board for each passenger (sum of 'SibSp and Parch'). Finally, I dropped the columns that were either irrelevant for the machine learning model or that had been transformed into numerical values.


With this clean dataset, I applied a Gradient Boosting classifier from scikit-learn library. I did a grid-search on three hyper-parameters (learning rate, max_depth and n_estimators) and got the best model with an accuracy score of 82% for a learning rate of 0.01, max_depth of 3 and n_estimators of 300. This accuracy score is on the mean of cross validation sets created by the grid search process (By default, the GridSearchCV's cross validation uses 3-fold KFold).

## Files details

- train.csv: dataset used for training
- test.csv: dataset used for final prediction
- results-rf.csv: dataframe with only two columns (passgenr ID and survived). Used for submission on Kaggle website.
- Titanic.ipynb: Jupyter notebook with all the code for data exploration, data visualization, data cleaning and machine learning.
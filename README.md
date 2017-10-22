# Kaggle Competition - Titanic

![alt text](titanic.jpg)

## Short summary

This task requires participants to predict the outcome of grant applications for the University of Melbourne.

## Methodology

I started by cleaning the dataset as it was not amenable for study in the current state. Each row contained 15 columns that were repeated 15 times (225 columns). Each block consisted of information regarding a researcher and each row consisted of one application that included up to 15 researchers.

I started by splitting these blocks and creating a new dataframe with one line per researcher. This made it much easier to  "group by" and create new columns.

I then started to explore each feature (column) and compiled new column from the existing ones. For non-numerical variables, I either got dummies out of it or created categorical variables.

Once I got a proper dataset with valuable columns (close to 100 features in the end), I then applied a random forest model to it. The result was good with a AUC scoring of 94%.

## Files details

- data folder: datasets used
- data_wrangling.py and data_wrangling2.py: are the python code for cleaning the data set. Running data_wrangling.py returns a new dataframe that will be used for the machine learning.
- Machine Learning.ipynb: this notebook contains our machine learning code (random forest with scoring)
- other files: drafts notebooks used during first exploration of the data
# Titanic-ML

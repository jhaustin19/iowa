# Executive Summary

- This project was part of a Kaggle competition to correctly predict the sale price of a home in Ames, Iowa
- My best model achieved an RMSE of about $25,000. For reference, the winner of the competition achieved an RMSE of about $18,000
- Although I am reasonably happy with my RMSE, it's clear to me now that I needed to make use of more features, and perhaps should have resorted to more logical forms of imputation. These both present obvious room for improvement

# Background

As mentioned, this project was part of a Kaggle competition.

# Data Acquisition & Cleaning

Because this was a Kaggle competition, the dataset was provided for me, but it did not come in anything close to perfect condition. There were a large number of columns with improper datatypes as well as a good chunk of missing data. For this missing data, I chose to use a form of cohort mean imputation, wherein I filled missing values with the average from homes in the surrounding area.

# EDA

EDA confirmed that the features most correlated with sale price were things you'd intuitively expect. There were two homes that appeared to be selling for far less than they should have (maybe due to a intra-family sale) so they were dropped.


# Modeling

I fit a variety of models, but the one that performed the best ended up being a Lasso model with polynomial features.

# Conclusions

- My RMSE is not bad, perhaps even good enough for the model to be deployed
- However, there is obvious room for improvement
    - Most notably, I should have made use of more of the features available to me. In particular, the neighborhood a home is in was not used by my model because of the simple fact that I didn't dummify the feature
    - In addition, given the shear number of features, it would be wise to try something like principipal component regression for dimensionality reduction

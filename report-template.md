# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
    * The purpose of this analysis was to determine if we can reliably use the provided financial information to predict whether or not someone will default on a loan.
* Explain what financial information the data was on, and what you needed to predict.
    * To predict whether or not someone would default on a loan, we looked at several points of financial information, including the loan size and interest rate, the borrower income, the borrower's debt to income ratio, the number of accounts the borrower has, any derogatory marks on their accounts, and their total debt.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
    * I started by separating the value we are trying to predict, in this case loan status, from the input financial values, then splitting the data into training and testing sets. From here, I was able to create a logistic regression model and train it with the training data, then make predictions with the testing data. Finally, I evaluated the model's performance by generating a confusion matrix and classification report.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).
    * Logistic Regression: A logistic regression model uses a set threshold to create binary predictions. Above the threshold, everything becomes 1, below the threshold, everything is 0. In this case, 1 indicates default, while 0 indicated a healthy loan. 
    * Confusion Matrix: A confusion matrix shows us the number of true negatives and positives vs the number of predicted values. Left to right and top to bottom, we can see the number of predicted non-default loans were actually good loans, the number of predicted non-default loans that ended up defaulting, the number of predicted default loans that did not default, and the number of predicted default loans that did default. Low numbers in the upper right and lower left sections shows that the model is fairly accurate.
    * Classification Report: A classification report gives us a different view of how good our model is. It displays Accuracy, Precision, and Recall scores to give a fairly simple explanation of how accurate our model is.

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.


    * Accuracy: Accuracy is a simple percentage of how often the model is correct, or how many correct predictions vs total predictions were made.
    * Precision: Precision is the ratio of correct positive predictions vs all positive predictions. In this case, the ratio of predicted correct defaults to total predicted defaults, or percentage of predicted defaults that were actual defaults
    * Recall: Recall is the ratio of correct positive predictions to all predictions for that class. In this case, the ratio of predicted correct defaults to all defaults.


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?
    * The logistic regression model makes the most sense for this data. We are looking at a binary decision, to either issue a loan or not.
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
    * In this case, accuracy in predicting healthy loans is more important. While it would be unfortunate for the borrower, a bank would much rather avoid a healthy loan that the model says is high-risk, rather than give out a predicted healthy loan and have it default. With 100% precision in predicting healthy loans, the bank can have a lot of confidence that they aren't issuing loans that will later default.

If you do not recommend any of the models, please justify your reasoning.

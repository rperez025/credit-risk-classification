# Module 20 - Supervised Learning

## CREDIT RISK ANALYSIS REPORT
## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Purpose of analysis: The purpose of this analysis is to use various techniques to train and evaluate a model based on loan risk. I used a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers. 
* Dataset: The dataset (['lending_data.csv'](https://github.com/rperez025/credit-risk-classification/blob/main/Credit_Risk/lending_data.csv)) included the following financial information:
  - loan_size
  - interest_rate
  - borrower_income
  - debt_to_income
  - num_of_accounts
  - derogatory_marks
  - total_debt
  - loan_status: This column contains either 0 or 1, where 0 means that the loan is healthy and 1 means that the loan is at high risk of defaulting.
* What am I predicting? I will be using the model to predict whether a loan is healthy or at risk of defaulting (i.e., loan status).
* Machine learning process I went through as part of this analysis:
  - Read the (['lending_data.csv'](https://github.com/rperez025/credit-risk-classification/blob/main/Credit_Risk/lending_data.csv)) data into a Pandas DataFrame after dropping it in to the Resources folder in Google Colab.
  - Created the labels set (y) from the “loan_status” column, and then created the features (X) DataFrame from the remaining columns.
  - Split the data into training and testing datasets by using train_test_split.
  - Fit a logistic regression model by using the training data (X_train and y_train).
  - Saved the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.
  - Evaluated the model’s performance by performing the following:
     * Calculated the balanced accuracy score of the model.
     * Generated a confusion matrix.
     * Printed the classification report.
* Methods used: I first used the  LogisticRegression model on the original fitted dataset. Upon observation that the data was highly overweighted towards one of the target variables (healthy loans = 0), I employed the RandomOverSampler to reduce the imbalances, and then LogisticRegression was applied to the oversampled data.

## Results

This section describes the balanced accuracy scores, precision, and recall scores for the two machine learning models used for this analysis. Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1: Logistic Regression Model with Original Data
  
  The following are the key results drawn from the Machine Learning Model 1 results:
  
  ![ML Model 1](https://github.com/rperez025/credit-risk-classification/blob/main/Images/ClassificationRptLogRegOriginal.png)

  - Machine Learning Model 1 does a good job in predicting both the healthy and the high-risk loans based on the high accuracy score of 99% and balanced accuracy score of 94%. However, I noted that the data is imbalanced as 96.77% of the target values (75036 out of 77536) are for the healthy loans.
    
  - Next, this model has a precision score of 100% for the healthy loans and 87% for the high-risk loans. This can be attributed to the imbalance in the data (similar to the above). The precision scores imply that the model correctly classified healthy loans as positive 100% of the time. In contrast to the high-risk loans, the model predicted high-risk loans correctly as such only 87% of the times.
  
  - Lastly, this model has a recall score of 100% for the healthy loans and 89% for the high-risk loans. The recall scores imply that for all the instances where the loans were actually healthy, 100% of the times they were classified correctly. However, for all the instances where the loans were actually high-risk, they were classified correctly 89% of the times.


* Machine Learning Model 2: Logistic Regression Model with Random Oversampling of Data

  The following are the key results drawn from the Machine Learning Model 2 results:
  
  ![ML Model 2](https://github.com/rperez025/credit-risk-classification/blob/main/Images/ClassificationRptLogRegROS.png)

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

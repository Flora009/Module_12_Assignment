# Module 12 Report 

## Overview 

* Purpose of the analysis

    - Use a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.
    - Compare the model with original data and random oversampling data, analyze the result and find which one works better in identifying the high risk loans.

* Financial information from the data includes:
     - loan size
     - interest rate
     - borrower's income
     - debt to income ratio
     - number of accounts
     - derogatory marks
     - total debt
     - loan status
* Goal:
     - predict whether a loan status is high risk or not by using logistic regression model with the historical data


* Stages of the machine learning process I went through as part of this analysis
    - import data
    - seperate the data into target and feature datasets
    - encode the data
    - split the data into training and testing datasets
    - scale the data
    - import the resampling techniques (random oversampling)
    - resample the X and y training sets to make the value counts between classes approximately equal
    - instantiate the classified model
    - fit the model with the resampled data
    - generate the predictions
    - reveiw the results


* Methods you used  
    - Logistic Regression: 
    - Ramdom oversampling:

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Accuracy      ： 0.99
  * Precision     ： 0.84
  * Recall        ： 0.98

* Machine Learning Model 2:
  * Accuracy      ： 0.99
  * Precision     ： 0.83
  * Recall        ： 0.99

## Summary

The logistic regression model fit with oversampled data seems working better than with original data
- F1-score and accuracy are the same with the original data.
- Recall for 1 (high risk) predictions is higher (0.99) than the previous original data (0.98), which indicateds of all the loans that actually were in high risk, the model with the oversampled data works better in catching them correctly.
- Precision for 1 (high risk) predictions is lower (0.83) than the previous original data(0.84), which indicateds for the ones that are predicted as high risk loans by this model with the resampled data, the rate of correctness is lower. 
This higher recall comes with the cost of lower precision.

Performance depend on the problem we are trying to solve
- For this particular case, it is more important to predict the `1`'s than to predict the `0`'s since we care much more about high risk loans and want to pick up and avoid the high risk ones
- We don't want to miss any potential high risk loans, so the recall rate with higher scores may works better for us.
- Even if the precision is lower than the original one, we can always look further into the high risk loans and figure out it is truly high risk or not
- Accuracy is not that important since the ones with high risk lables are much less than the normal ones which end up with a very high accuracy score

__*Recommendations: For the analysis and reasons above, I'll recommend the model using resampled data for better predictions of the high risk loans.*__
    



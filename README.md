# Credit Fraud Classification Model 


## Overview of the Analysis

The purpose of this project is to develop a machine learning algorithim to predict whether a loan would be good, or bad (i.e. possible default in the future)

To do so, the following features would threaded through a logistic regression model. 

| loan_size | interest_rate | borrower_income | debt_to_income | num_of_accounts | derogatory_marks | total_debt |
|----------:|--------------:|----------------:|---------------:|----------------:|-----------------:|-----------:|

The dataset suffers through a rare-case where the status of defaulted loans is signficantly lower than healthy loans. Resampling would later be used to address the problem in the results section. 

| loan_status | Frequency | 
|------------:|----------:|
|           0 |     75036 |  
|           1 |      2500 |  

0 - healthy loan || 
1 - defaulted loan 

Based on PCA and visualization of the data, the pattern suggest that a linear classification method (logistic regression) should be applied - followed by resampling. 

![image](https://user-images.githubusercontent.com/89043234/228358870-1075fd8c-2f9c-43e3-8cc8-c8e1749033e9.png)

## Results

* Machine Learning Model 1: Logistic Regression (Before Resampling)

| precision | recall | f1-score |
|----------:|-------:|---------:|
|         0 |   1.00 |     1.00 |
|         1 |   0.86 |     0.91 |
|  accuracy |   0.99 |    15508 |

* Machine Learning Model 2: Logistic Regression (After Resampling)

| precision | recall | f1-score |
|----------:|-------:|---------:|
|         0 |   1.00 |     0.99 |
|         1 |   0.85 |     0.99 |
|  accuracy |   0.99 |    15508 |


## Summary

The logistic regression models overall are better at predicting healthy loans (0) relative to high-risk loan. This is expected due to the significant disparity between healthy and high-risk loans. However, the oversampled data still predicts healthy loans (0) relatively better than high-risk loan (1). As seenm, the recall has significantly improved for high-risk loans at a slight sacrifice of recall for healthy loans - and should be the recommended model to predict unseen data. 

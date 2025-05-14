## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* The purpose of this analysis is to use supervised machine learning to classify a loan type as either `0` (healthy) or `1` (high-risk)
* The dataset provided was titled lending_data.csv and contained anonymous loan data with the following categories
  * loan_size,interest_rate,borrower_income,debt_to_income,num_of_accounts,derogatory_marks,total_debt,loan_status
* Here is some preliminary statistics to get a feel for the data
loan_size interest_rate	borrower_income	debt_to_income	num_of_accounts	derogatory_marks	total_debt	loan_status
count	77536.000000	77536.000000	77536.000000	77536.000000	77536.000000	77536.000000	77536.000000	77536.000000
mean	9805.562577	7.292333	49221.949804	0.377318	3.826610	0.392308	19221.949804	0.032243
std	2093.223153	0.889495	8371.635077	0.081519	1.904426	0.582086	8371.635077	0.176646
min	5000.000000	5.250000	30000.000000	0.000000	0.000000	0.000000	0.000000	0.000000
25%	8700.000000	6.825000	44800.000000	0.330357	3.000000	0.000000	14800.000000	0.000000
50%	9500.000000	7.172000	48100.000000	0.376299	4.000000	0.000000	18100.000000	0.000000
75%	10400.000000	7.528000	51400.000000	0.416342	4.000000	1.000000	21400.000000	0.000000
max	23800.000000	13.235000	105200.000000	0.714829	16.000000	3.000000	75200.000000	1.000000

* After loading in the dataset we wanted to use a supervised machine learning model to predict whether a loan would be healthy or high-risk
  * Our two categories were `0` (healthy) and `1` (high-risk) and the loan_status column was chosen as our y column vector
  * The remaining features were then split up to use as our X matrix for our LogisticRegression Model
  * Using the train_test_split function from sklearn we split our data into two parts one for Training the model (75%) and one for testing its usefulness (25%)
  * With the new split data we were able to train and test our LogisticRegression Model and generate a confusion matrix to evaluate it's performance


## Results

* The precision matrix we got from our model is as follows 

[18655,   110]
[   36,   583]

* From this we were able to generate a classification report to gauge precission, recall, and overall accuracy of our model 

              precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.84      0.94      0.89       619

    accuracy                           0.99     19384
   macro avg       0.92      0.97      0.94     19384
weighted avg       0.99      0.99      0.99     19384


## Summary

The logistic regression model used does a very good job predicting the healthy loans `0` with both a precision and recall of nearly 100 percent. Meaning that nearly all of the healthy loans were correctly identified and the model correctly predicted healthy loans 99% of the time. 

However the model struggled more with the hig-risk loans `1` as it was only able to identify 84% of them corrrectly. It did better at predicting them at a 94% rate, but this was still below what it accomplished wiht the healthy loans. I believe the reason for the much smaller sample of high-risk loans (619=583+36) compared to the number of healthy loans (18756=18655+110).

Overal the logistic regression model predicted the data set very well with a global precision avergage of 92%, and a wegithed average of 99%. With a more balanced data set there is potential for even further improvement from this model. 

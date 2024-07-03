# Problem Statements
A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash.
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. 
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.
We have to build a classification model to predict whether a transaction is fraudulent or not.
# Data summary
- Total Transactions: 284,807
- Fraudulent Transactions: 492 (0.172% of all transactions)

# Exploratory Data Analysis
simple data exploration using means of all the variables by defaulted person against not defaulted. also a correlation matrix between all the variables to find variables with strong correlation that can be reduced. And a linear regression to explore how strong is the correlation of independent variables (features) to the dependent variable (default).
![image](https://github.com/Rishitha9/Credit_card_fraud_prediction/assets/56880713/9e429975-bb42-442c-ab40-873272197a07)
![image](https://github.com/Rishitha9/Credit_card_fraud_prediction/assets/56880713/1151b50d-45b9-4e35-8f59-c12e792c5f16)
![image](https://github.com/Rishitha9/Credit_card_fraud_prediction/assets/56880713/7a4627f8-763f-456a-8f08-9ec880be2b7b)
![image](https://github.com/Rishitha9/Credit_card_fraud_prediction/assets/56880713/26c9d30b-2dc7-4c59-87dc-9287547e75b7)


Data Cleaning-
There are no null values

Train and split-
Test which model most accurately predict the test data

I chose the 2 most accurate classifying algorithms. Using these 2 algorithms I tried to fit models but with data that was over sampled using SMOTE - Synthetic Minority Over-Sampling Technique.

Test the prediction accuracy of the fitted models from step 4 and compare them to the result , before the resample. To examine if the oversampling of the data contributes to our ability accurately predict the outcome, i.e credit card clients default.

I choose the most accurate algorithm then Test different hyper parameters for this algorithm using a cross-validated grid-search over a parameter grid ('GridSearchCV' algorithm of scikit-learn package), to find the parameters that can give a better predictive result than the default hyper parameters used in previous steps.



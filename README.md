The dataset train.csv is used for training. The train dataset had 2,45,725 records with 11 features.
The dataset consisted the following attributes :

ID : Unique Identifier for a row
Gender : Gender of the Customer
Age : Age of the Customer (in Years)
Region_Code : Code of the Region for the customers
Occupation : Occupation Type for the customer
Channel_Code : Acquisition Channel Code for the Customer (Encoded)
Vintage : Vintage for the Customer (In Months)
Credit_Product : If the Customer has any active credit product (Home loan, Personal loan, Credit Card etc.)
Avg_Account_Balance : Average Account Balance for the Customer in last 12 Months
Is_Active : If the Customer is Active in last 3 Months
Is_Lead(Target) : If the Customer is interested for the Credit Card (0 : Customer is not interested , 1 : Customer is interested)

      
      
Some of the data insights are given below. (For the detail EDA please refer to the ipynb notebook)

Customers aged between 40-60 have greater interest in credit cards whereas customers in their 20s and 30s and less interested

Salaried person are less likely to take up credit cards. Only among Entrepreneur the number of customers interested to take up credit cards is more. 66% of total Customers falling in Entrepreneural category in Occupation have shown interest in the past followed by 27.6% Self Employed, 24.5% in Others category and 16% Salaried.There are only 2 Entrepreneurs who don't have any credit product.


Number of Customers having credit products who are interested in Credit Card is more than those who donot have a Credit Product.
. Data Cleaning
The Missing Value in the Credit_Product column is imputed with No_Info
3. Feature Engineering
The categorical features (Gender, Region_Code, Occupation, Channel_Code, Credit_Product, Is_Active) were One Hot Encoded.
4. Oversampling (Handling Class Imbalance in Target Feature)
About 76.27% customers are not interested in credit card, and about 23.72% are interested in credit card. To address this imbalance Oversampling techniques like SMOTE is used.
5. Modelling and Hyperparameter Tuning
In Modelling both LightGBM and Xgboost is used.
For combining the predictions made by XGBoost and Light GBM, stacking is used
The models are tuned using Randomized Search CV
To check for overfitting 5 kfold cross validation was performed
      
1. Data Exploration and Analysis: Conduct thorough data exploration and analysis to gain insights into the data's characteristics, patterns, and relationships. Use appropriate visualizations and descriptive statistics to understand the data better.this step features having missing values and outliers, target variable distribution, numerical feature distribution, categorical feature distribution, Univariate and Bivariate Analysis was performed.
    2. Data Preprocessing: Clean, preprocess, and transform the data to make it suitable for modeling. Handle missing values, outliers, and data inconsistencies appropriately.
    3. Feature Engineering: Create new features or transform existing features to improve model performance and capture relevant information from the data.
    4. Model Selection: Choose appropriate machine learning algorithms or statistical models based on the problem type and data characteristics. Consider the trade-offs between interpretability and predictive power.
    5. Model Training and Evaluation: Split the data into training and test sets and train the model on the training data. Evaluate the model's performance on the test data using relevant evaluation metrics.
    6. Model Interpretability: Pay attention to model interpretability, especially if the project has real-world implications, use feature importance to explain model predictions.
    7. Documentation: Provide clear and comprehensive documentation for your project. Describe the problem statement, data sources, data preprocessing steps, feature engineering, model selection, and evaluation metrics.
    8. Data Visualization: Use effective data visualizations to communicate insights and model results. Visuals should be clear, informative, and visually appealing.
    9. Model Deployment: Consider the deployment of the trained model in a real-world scenario if applicable. Discuss how the model can be integrated into an existing system or make predictions in real-time.

Limitation and what can be improved
Combine this model with with a regression model to predict how much of a credit limit an applicant will be approved for.
Hyperparameter tuning with grid search or random search.
Better interpretation of the chi-square test
Retrain the model without the least predictive features

Why choose recall as metrics: Since the objective of this problem is to minimize the risk of a credit default, the metrics to use depends on the current economic situation:

During a bull market (when the economy is expanding), people feel wealthy and are employed. Money is usually cheap, and the risk of default is low because of economic stability and low unemployment. The financial institution can handle the risk of default; therefore, it is not very strict about giving credit. The financial institution can handle some bad clients as long as most credit card owners are good clients (aka those who pay back their credit in time and in total).In this case, having a good recall (sensitivity) is ideal.

During a bear market (when the economy is contracting), people lose their jobs and money through the stock market and other investment venues. Many people struggle to meet their financial obligations. The financial institution, therefore, tends to be more conservative in giving out credit or loans. The financial institution can't afford to give out credit to many clients who won't be able to pay back their credit. The financial institution would rather have a smaller number of good clients, even if it means that some good clients are denied credit. In this case, having a good precision (specificity) is desirable.

Note: There is always a trade-off between precision and recall. Choosing the right metrics depends on the problem you are solving.

Conclusion: Since the time I worked on this project (beginning 2022), we were in the longest bull market (excluding March 2020 flash crash) ever recorded; we will use recall as our metric.



Lessons learned and recommendation

Based on this project's analysis, income, family member headcount, and employment length are the three most predictive features in determining whether an applicant will be approved for a credit card. Other features like age and working employment status are also helpful. The least useful features are the type of dwelling and car ownership.
The recommendation would be to focus more on the most predictive features when looking at the applicant profile and pay less attention to the least predictive features.

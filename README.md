    1. Data Exploration and Analysis: Conduct thorough data exploration and analysis to gain insights into the data's characteristics, patterns, and relationships. Use appropriate visualizations and descriptive statistics to understand the data better.
	
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

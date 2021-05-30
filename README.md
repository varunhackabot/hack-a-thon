# hack-a-thon
Problem Statement:

Credit Card Lead Prediction
Happy Customer Bank is a mid-sized private bank that deals in all kinds of banking products, like Savings accounts, Current accounts, investment products, credit products, among other offerings.
 
The bank also cross-sells products to its existing customers and to do so they use different kinds of communication like tele-calling, e-mails, recommendations on net banking, mobile banking, etc. 
 
In this case, the Happy Customer Bank wants to cross sell its credit cards to its existing customers. The bank has identified a set of customers that are eligible for taking these credit cards.
 
Solution:
Step-01(Loading and Cleaning The Data)
 
From the given dataset, the data consist of 7 categorical columns ( ID                   
Gender ,Region_Code , Occupation, Channel_Code, Credit_Product , Is_Active) and 3 numerical columns (age,vintage and avg_account_balance) .
Approximately 17% of the values were missing from credit_product. The missing values are imputed using mode since it is categorical data.
There were positive outliers present in avg_account_balance and upon visualizing it using distplot, the plot was log normal. Instead of removing the outliers, the outliers are imputed using log-normal or using box cox transformation and forming a normal distribution.
 
Step-02(Performing Exploratory Data Analysis)
Univariate Analysis:
Channel Code: From the count plot, X1 has 50% occurrence of total data in channel code.X3 and X2 have the same number of occurrences in channel code which is about 30%. 
Occupation: From the count plot almost 40% of people are self-employed and approx 30% of them are salaried and others. Approx 2% of them are entrepreneurs.
 
Bivariate Analysis:
 
Occupation vs Age: From the barplot, self_employed and Entrepreneur have almost equal age, while the salaried person has lower age compared to others.
Gender vs Age: The dataset has more aged males compared with women.
Occupation vs Vintage: Entrepreneurs have a higher vintage compared to the rest of occupation people. Self-employed and others have almost equal vintage with banks
 
 
.
Step-03(Feature Engineering)
The ID column is dropped from the dataset to train the model with high accuracy since the Id column does not hold any significant value. By dropping the column, features become less which gives much better results.
Label encoder is applied to categorical columns to convert them in terms of numerical for better processing of data when training the model for the given dataset.
 
 
 
Step-04(Training the Model)
The dataset is very large in nature and the majority of our data is now in the form of 0 and 1 and requires classification type algorithms to train the model accurately. For this, the LGBM algorithm is used as this algorithm is an extension of the decision tree and trains much faster. The model is split using k-folds to preserve the class ratio of the dataset.
 
 
Step-05(Result) 
 
From feature importance, age dominates as the most important feature which decides customers who show higher intent towards a recommended credit card. Vintage serves as the second most important feature which is slightly less than the age parameter in prediction. Credit Product, occupation, Average account balance, and region code serves almost equally important features.

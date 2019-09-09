# Fraud Detection using Logistic Regression

In today's world, when everything is digitized, it becomes extremely necessary that companies and organizations are able to recognize fraudulent transactions so that customers are not cheated and charged falsely. This notebook shows how credit card transaction data can be used to visualize and train a logistic regression model in order to predict whether a transaction is fraud or not, using different features.

## Dataset

Dataset : https://www.kaggle.com/mlg-ulb/creditcardfraud


The datasets contains transactions made by credit cards in September 2013 by european cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Due to confidentiality issues, the dataset is unable to provide the original features and more background information about the data. Features V1, V2, ... V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. 

* Feature ```Time``` contains the seconds elapsed between each transaction and the first transaction in the dataset. 
* The feature ```Amount``` is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. 
* Feature ```Class``` is the response variable and it takes value 1 in case of fraud and 0 otherwise.

## Model

I have made a pipeline that consists of a ```Standard Scaler```, a ```Logistic Regressor```, and ```Stochastic Gradient Descent``` as the optimization technique. 
To score the model, I have used ```matthews_corrcoef``` and ```GridSearchCV``` to perform cross-validation iterativelty with 5-folds.

The model achieves the best score of ~ ```0.68``` on the validation data and ~ ```0.69``` on the testing data.

## Use cases
This regressor can be used with ```REST``` APIs in order to provide a transaction analytics service. It can also be deployed on the web using different web frameworks like Django or Flask.
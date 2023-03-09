# Credit Card Fraud detection with Classifiers

## Background
Most of my recent ML projects had been using regression algorithms.  As such I wanted a mini project to work on that would help me to practice my my use of classifers and refreshing my understanding of evaluating performance of classifiers.  In particular, I wanted to improve my understanding of working with heavily imbalanced data, such as varying the metrics for evaluating models and using resampling techniques such as ADASYN to deal with the imbalance.

The original data can be found [here](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud). The dataset contains transactions made by credit cards in September 2013 by European cardholders. 
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

## Context

It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.  However, it is important that the predictions for fraudulent transactions are precise as too many false positives would result in a large nunmber of genuine purchases being stopped or delayed.

## Scoring

Since 98% of the dataset is class 0, using accuracy score (or any of precision, recall or f1 scores for class 0) would be ineffective as predicting every transacation as class 0 would still score 98% accuracy.  Instead, AUC PR curve is used to score the final model.

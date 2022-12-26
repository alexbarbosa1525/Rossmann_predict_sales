# Rossmann Drug Store Sales Prediction

Sales forecast for the stores of the european drugstore chain Rossmann.
An end-to-end Data Science project with a regression adapted for time series as solution to forecast sales for the stores of the european drugstore chain Rossmann.

This repository contains the solution for a Kaggle competition problem: https://www.kaggle.com/c/rossmann-store-sales

This project is part of the "Data Science Community" (Comunidade DS), a study environment to promote, learn, discuss and execute Data Science projects.

Project Planning:

The project was developed based on the CRISP-DS (Cross-Industry Standard Process - Data Science, a.k.a. CRISP-DM) project management method, with the following steps:

- Business Understanding;
- Data Collection;
- Data Cleaning;
- Exploratory Data Analysis (EDA);
- Data Preparation;
- Machine Learning Modelling and fine-tuning;
- Model and Business performance evaluation / Results;
- Model deployment.


## Business problem:
The Rossmann company is a private drugstore chain based on Germany, that operates 3000 drustores in 7 different countries.  
The stores of the Rossmann drugstore chain need to be restored and the CEO needs to decide how much is going to be dedicated to the restoration of each one. To support this decision, the Analytics team is asked to present a sales forecast for each store during a period of six weeks, alongside with the total income expected in the chain. This forecast also informs the CEO which store is able to account for its own restoration with the income within this period.

## Business Assumptions
All stores contain a basic sortment, but some of them contain (different kinds of) extra sortments.
The store's opening on weekends and holidays vary from place to place.
The stores participate in seasonal promotions. In some of these cases, the promotion is continued for a longer time.

## Dataset

The dataset has 1017209 rows and 17 columns that represets features which explain behaviors of the target variable Sales.

- Id - an Id that represents a (Store, Date) duple within the test set
- Store - a unique Id for each store
- Sales - the turnover for any given day (this is what you are predicting)
- Customers - the number of customers on a given day
- Open - an indicator for whether the store was open: 0 = closed, 1 = open
- StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
- SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools
- StoreType - differentiates between 4 different store models: a, b, c, d
- Assortment - describes an assortment level: a = basic, b = extra, c = extended
- CompetitionDistance - distance in meters to the nearest competitor store
- CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened
- Promo - indicates whether a store is running a promo on that day
- Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
- Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2
- PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store

## Solution Strategy
The strategy adopted was the following:

Step 01. Data Description: I searched for NAs, checked data types (and adapted some of them for analysis) and presented a statistical description.

Step 02. Feature Engineering: New features were created to make possible a more thorough analysis.

Step 03. Data Filtering: Entries containing no information or containing information which does not match the scope of the project were filtered out.

Step 04. Exploratory Data Analysis: I performed univariate, bivariate and multivariate data analysis, obtaining statistical properties of each of them, correlations and testing hypothesis (the most important of them are detailed in the following section).

Step 05. Data Preparation: Numerical data was rescaled, categorical data was transformed and cyclic data (such as months, weeks and days) was transformed using mathematical trigonometrical functions.

Step 06. Feature selection: The statistically most relevant features were selected using the Boruta package.

Step 07. Machine learning modelling: Some machine learning models were trained. The one that presented best results after cross-validation went through a further stage of hyperparameter fine tunning to optimize the model's generalizability.

Step 08. Model-to-business: The models performance is converted into business values.

Step 09. Deploy Model to Production: The model is deployed on a cloud environment to make possible that other stakeholders and services access its results.

5. Machine Learning Model Applied and Model Performance:

The following machine learning models were trained:

 - Mean of the target variable (baseline) Model;
 - Linear Regression Model;
 - Linear Regression Regularized Model - Lasso
 - Random Forest Regressor;
 - XGBoost Regressor.

All of them were cross-validated.

## Business results
The gross expected income of the majority of stores is in the range between R$5000.00 and R$22000.00. The chain is expected to obtain R$289,822,112.00, with best and worst case scenarios of R$290,808,412.17 and R$288,835,860.27, respectively. These scenarios are predicted using the mean absolute percentage error. The same statistical error is applied to each store, individually.

## Next Steps:

Implement a method were the CEO and Managers can access the results per store (App, message, etc.)
Try to implement new features, to optimize the results with XGBoost Regressor.
Present all the Hiphotesis analyzed during the project.




# LICENSE

MIT LICENSE
# All Rights Reserved - Comunidade DS 2021

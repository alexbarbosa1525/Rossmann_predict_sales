# Rossmann_store_sales_prediction

Sales forecast for the stores of the european drugstore chain Rossmann.

## Business problem
The stores of the Rossmann drugstore chain need to be restored and the CEO needs to decide how much is going to be dedicated to the restoration of each one. To support this decision, the Analytics team is asked to present a sales forecast for each store during a period of six weeks, alongside with the total income expected in the chain. This forecast also informs the CEO which store is able to account for its own restoration with the income within this period.

## Business results
The gross expected income of the majority of stores is in the range between R$5000.00 and R$22000.00. The chain is expected to obtain R$289,822,112.00, with best and worst case scenarios of R$290,808,412.17 and R$288,835,860.27, respectively. These scenarios are predicted using the mean absolute percentage error. The same statistical error is applied to each store, individually.

## Business Assumptions
All stores contain a basic sortment, but some of them contain (different kinds of) extra sortments.
The store's opening on weekends and holidays vary from place to place.
The stores participate in seasonal promotions. In some of these cases, the promotion is continued for a longer time.

## Solution Strategy
The strategy adopted was the following:

Step 01. Data Description: I searched for NAs, checked data types (and adapted some of them for analysis) and presented a statistical description.

Step 02. Feature Engineering: New features were created to make possible a more thorough analysis.

Step 03. Data Filtering: Entries containing no information or containing information which does not match the scope of the project were filtered out.

Step 04. Exploratory Data Analysis: I performed univariate, bivariate and multivariate data analysis, obtaining statistical properties of each of them, correlations and testing hypothesis (the most important of them are detailed in the following section).

Step 05. Data Preparation: Numerical data was rescaled, categorical data was transformed and cyclic data (such as months, weeks and days) was transformed using mathematical trigonometrical functions.

Step 06. Feature selection: The statistically most relevant features were selected using the Boruta package.

Step 07. Machine learning modelling: Some machine learning models were trained. The one that presented best results after cross-validation went through a further stage of hyperparameter fine tunning to optimize the model's generalizability.

Steps to do: 

Step 08. Model-to-business: The models performance is converted into business values.

Step 09. Deploy Model to Production: The model is deployed on a cloud environment to make possible that other stakeholders and services access its results.


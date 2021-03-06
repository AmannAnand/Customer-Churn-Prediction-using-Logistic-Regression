
# Customer Churn Prediction
<img src="https://user-images.githubusercontent.com/84275757/173112022-31911364-f595-41e0-acc0-cd8f4ec28de5.jpg" width="400" height="200" />




## :small_blue_diamond: Project Overview

•	Utilized dataset which contained many features of customer demographics, transaction data, and bank branch data required for predicting customer churn.

•	Performed extensive Exploratory Data Analysis (EDA) to select the best features.

•	Models were trained using logistic regression and evaluated using different evaluation metrics. The rfe_top_10 model gave score of 
AUC-ROC=0.8118, Recall=0.2253 and outperformed all three models.

## :small_blue_diamond: Motivation/Purpose

•	Customer churn occurs whenever a customer stops taking the services of service providing company. It is a big issue for many businesses because acquiring new customers often costs more than retaining existing ones. 

•	As a result, tools for developing and implementing customer retention models (churn models) are essential Business Intelligence applications.

•	Churning can occur as a result of low customer satisfaction, aggressive competitive strategies, new products, regulations, and other factors in today's dynamic market environment. 

•	Churn models are designed to detect early churn signals and identify customers who are more likely to leave voluntarily and transfer their businesses to a competitor.

## :small_blue_diamond: Dataset Overview

Dataset of a bank with 225,000 customers has been used, which is facing the problem of stagnating customer balances since the last 3 months.


There are multiple variables in the dataset which can be cleanly divided in 3 categories:
### Demographic information about customers
customer_id - Customer id

vintage - Vintage of the customer with the bank in number of days

age - Age of customer

gender - Gender of customer

dependents - Number of dependents

occupation - Occupation of the customer
city - City of customer (anonymised)
### Customer Bank Relationship
customer_nw_category - Net worth of customer (3:Low 2:Medium 1:High)

branch_code - Branch Code for customer account

days_since_last_transaction - No of Days Since Last Credit in Last 1 year
### Transactional Information
current_balance - Balance as of today

previous_month_end_balance - End of Month Balance of previous month

average_monthly_balance_prevQ - Average monthly balances (AMB) in Previous Quarter

average_monthly_balance_prevQ2 - Average monthly balances (AMB) in previous to previous quarter

current_month_credit - Total Credit Amount current month

previous_month_credit - Total Credit Amount previous month

current_month_debit - Total Debit Amount current month

previous_month_debit - Total Debit Amount previous month

current_month_balance - Average Balance of current month

previous_month_balance - Average Balance of previous month

churn - Average balance of customer falls below minimum balance in the next quarter (1/0)


## :small_blue_diamond: Problem Statement

What customer segments are more liekly to churn balances in the next quarter by at least 50% considering current quarter?

## :small_blue_diamond: Hypothesis Generation
Some of the hypotheses are listed below:

### Demographics
•	Are females less likely to churn than males?

•	Are young customers more likely to churn?

•	Are customers located in Tier-1 cities more likely to churn?

•	Are married people less likely to churn?

•	Are older customers less likely to churn?

•	Are customers in the lower income bracket more likely to churn?

•	Are customers in the middle income bracket more likely to churn?

•	Are customers in the higher income bracket more likely to churn?

### Behaviour
•	Are vintage customers less likely to churn?

•	Are customers with higher average balance less likely to churn?

•	Are customers dropping monthly balance high likely to churn?

### Psychographic
•	Do customers that are inherently more loyal less likely to churn?

•	Do customers that have interest in sports more likely to churn?

•	Do customers who go to movies often are highly likely to churn?

### Other factors
•	Customers getting a low rate of interest in fixed deposit compared to competitor banks are more likely to churn?

•	Customers getting a low rate of interest in recurring deposit compared to competitor banks are more likely to churn?

•	Customers incurring a high rate of interest in house loans compared to competitor banks are more likely to churn?


## :gear: Technologies Used
![Screenshot (151)](https://user-images.githubusercontent.com/84275757/173030213-f8e8a1d1-86d5-4782-abf1-928889fc6677.png)
<img alt="numpy" src="https://user-images.githubusercontent.com/84275757/173030594-fba1e76a-d6c5-4928-ac77-4057b1028025.png" width="200" height="200" />
<img src="https://user-images.githubusercontent.com/84275757/173031448-9e3e22df-53a6-480d-8a24-56c3b269a70a.png" width="250" height="200" />
<img src="https://user-images.githubusercontent.com/84275757/173031755-5d73c113-a4ca-4119-a693-885972be603b.png" width="350" height="150" />
<img src="https://user-images.githubusercontent.com/84275757/173031858-ebcd32fb-88d0-459a-8147-8fcec5b462d5.png" width="200" height="200" />
<img src="https://user-images.githubusercontent.com/84275757/173031918-1584d7ce-f852-4c47-a3bb-391fadff9a6d.png" width="300" height="200" />


## :small_blue_diamond: Methodology

:bulb: Note:- Please turn on Light theme in Github to see the below images properly (most captions and axes are not visible in dark theme).

<img src="https://user-images.githubusercontent.com/84275757/173101975-d54eb319-941e-46b4-9fe2-97f6c2a267b0.png" width="500" height="700" />

## :small_blue_diamond: Exploratory Data Analysis (EDA)
Some snapshots from EDA 
### Univariate Analysis

<img src="https://user-images.githubusercontent.com/84275757/173103836-eba4293a-7896-462f-aab2-586866534852.png" width="1000" height="300" />
<img src="https://user-images.githubusercontent.com/84275757/173103990-251cfdba-89d7-45ef-a07a-447e99425ea2.png" width="600" height="400" />

### Bivariate Analysis

<img src="https://user-images.githubusercontent.com/84275757/173104066-ca35dea8-7a66-4d96-ab52-dcc2373b0497.png" width="1000" height="300" />
<img src="https://user-images.githubusercontent.com/84275757/173104117-b84bfce8-c85f-4d26-abd3-21c7bf2e086b.png" width="600" height="400" />

### Multivariate Analysis

<img src="https://user-images.githubusercontent.com/84275757/173104598-4b09f363-39b6-4b28-9c6c-3f73eb6bf16f.png" width="700" height="400" />
<img src="https://user-images.githubusercontent.com/84275757/173104277-357b86c0-d23e-4128-95c2-4be34870b8b2.png" width="600" height="400" />

Complete EDA in detail can be seen in [EDA Notebook.](Customer_Churn_Prediction_EDA.ipynb)

## :small_blue_diamond: Conclusions from EDA
•	For debit values, we see that there is a significant difference in the distribution for churn and non churn and it might be turn out to be an important feature

•	For all the balance features the lower values have much higher proportion of churning customers

•	For most frequent vintage values, the churning customers are slightly higher, while for higher values of vintage, we have mostly non churning customers which is in sync with the age variable

•	We see significant difference for different occupations and certainly would be interesting to use as a feature for prediction of churn.


## :small_blue_diamond: Data Preproccessing

Done after EDA, to see any hidden patterns in raw data and avoid any bias.
### Missing values
Gender: It had some missing values but since there was a good mix of males and females and arguably missing values cannot be filled with any one of them. A seperate category was created by assigning the value -1 for all missing values in this column.

Dependents, occupation and city: The missing values in these columns were filled with mode of respective columns.

Days since Last Transaction: A fair assumption was made on this column as this is number of days since last transaction in 1 year, we can substitute missing values with a value greater than 1 year say 999.

### Preprocessing
There were a lot of outliers in the dataset especially when it comes to previous and current balance features. Also, the distributions are skewed for these features, so two steps were taken to deal with that here:

1. Log Transformation

2. 	Standard Scaler
 
## :small_blue_diamond: Model Building

Three separate models were built and trained using logistic regression.
1.	Model with all features 
2.	Model with baseline features
3.	Model with top 10 features obtained from reverse feature elimination (RFE)

## :small_blue_diamond: Evaluation metrics

Since this is a binary classification problem, we could use the following 2 popular metrics:
1.	Recall
2.	Area under the Receiver operating characteristic curve (AUC-ROC)

Now, we are looking at the recall value here because a customer falsely marked as churn would not be as bad as a customer who was not detected as a churning customer and appropriate measures were not taken by the bank to stop him/her from churning

The ROC AUC is the area under the curve when plotting the (normalized) true positive rate (x-axis) and the false positive rate (y-axis).
Our main metric here would be Recall values, while AUC ROC Score would take care of how well predicted probabilites are able to differentiate between the 2 classes.

Cross Validation (5 Fold) has been also used to prevent overfitting.

## :small_blue_diamond: Model Performance

The complete implementation of all models using logistic regression can be seen at [Customer Churn Prediction using Logistic Regression notebook.](Customer_Churn_Prediction_Logistic_Regression.ipynb)

The all features model gave best score of 
AUC-ROC=0.8058, Recall=0.2405

The baseline model gave best score of
AUC-ROC=0.7822, Recall=0.1236

The rfe_top_10 model gave best score of 
AUC-ROC=0.8118, Recall=0.2253

<img src="https://user-images.githubusercontent.com/84275757/173106395-4657cc7f-2da3-4055-b2aa-a760882e60a5.png" width="500" height="300" />


Thus, rfe_top_10 model performed the best among all the three models.




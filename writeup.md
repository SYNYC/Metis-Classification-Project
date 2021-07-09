# Loan Repayment Prediction

Sabrina Yang


## Abstract

The purpose of this project is to help lending institutions to determine which borrowers to lend to. In order to achieve this, I built a model to predict whether a borrower would repay their loan or not. Lenders will loan a principal amount out to borrowers and also charge interest. Once the principal is paid back in full at the end of the loan, the lender will make a significant profit. This is why they would prefer not to risk losing even a single dollar as this can greatly affect their profit. There are many variables and features associated with loans, which can be found on Lending Club’s website. However, I determined that 28 features are most likely to have the largest impact on the model and have analyzed these as such. By building a model that incorporates these features, the lender would be able to quickly discern which borrowers are most likely to repay or not repay their loans. 

## Design
The question of whether a client will pay or not can be solved by using supervised learning as a classification tool. Doing a hard prediction will help me predict whether the client will pay or not. The lending institution is concerned about losing any principal at all and so would rather not lend than to lose any money at all. So in this project, recall will be more focused than precision. As such, I took the F2 score as my critical examination tool.

## Data
The dataset is originally from [Lending Club](https://www.lendingclub.com/) with 28 features in total, some of which are numerical. The time period of the data is 3 years (2018 to 2021). 



## Methodology
*Data Collection and Manipulation*

1.	Gathered data from Kaggle.com and did feature engineering to cut down the features from 140+ to 28.
2.	Set aside the financial pro features

*Modeling*

1.	Logistic regression
2.	KNN
3.	Random Forest
4.	XGBoost
5.	Tuned the model by GridSearchCV

*Handling Class Imbalance*
1. Random Forest

	class_weight = "balance" to make it equal ratio

2. XGBoost

	The class imbalance for original dataset is 0.79 (negative) vs 0.20(positive), so the most accurate scale_pos_weight should be around 4, but GridSearchCV shows me 5 worked out well so I choose 5 to continue my tunning. The reason I didn't choose anything above 6 (even their F2 score were higher) is because I don't want my classes got too many positive samples versus negative cases, and I assume the ideal ratio should be balance like 1: 1.

## Tools

1. Sklearn 
  - LogisticRegression
  - RandomForestClassifier
  - GridSearchCV
  - Fbeta_score
  - Confusion_matrix
  - Classification_report
2. Xgboost - XGBClassifier
3. Numpy
4. Pandas


## Summary

The results as below shows __Fbeta 2 score = 0.589__  from XGBoost model that worked out the best out of other models after tuning hyperparameters: 

 		      xgb_5 = XGBClassifier(eval_metric='mlogloss',
                      				scale_pos_weight = 5,
                     		 		learning_rate = 0.05, 
                      				min_child_weight = 57, 
                     				max_depth = 5 ,
                      				n_estimators = 300,   
                      				n_jobs = -1 ,random_state =50,
                      				subsample = 0.5) 





<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/new/xgb5/score_0.589.png" >


In terms of feature importance, I found out that the top features related to Charge Offs(positive cases) are :
1.	__term_60__ is the most important with the highest coefficient 
    - a.	Term is the number of months that a borrower must pay monthly payments
    - b.	People who tend to default are usually ones with longer terms
    - c.	Paying their loan over a longer period of time is more difficult when the borrower is going through financial hardship
2.	__Home_ownership__
    - a.	The home ownership status provided by the borrower during registration or obtained from the credit report. Our values are: RENT, OWN, MORTGAGE, OTHER
    - b.	RENTis more likely to charge off than OWN
    - c.	OTHER is zero coef and thus not important

3.	__Inquiry_last_6mths__
    - a. 	The number of inquires in the past 6 months (excluding auto and mortgage inquiries)
    - b. 	more times of inquries got made in last 6 months can indicated the borrowers were under more financial stress or spending, so it could lead to more probabilty of failing to payback.
     
4.	__Installment__ 
    - a.	Installment is the monthly payment owed by the borrower if the loan originates
    - b.	The higher the monthly payment, the more likely a borrower cannot fulfill it and will charge off
5.	__Address State__
    - a. The state provided by the borrower in the loan application
    - b. I sorted all states into 4 categories : North East, West, South, and Central
    - c. West is more likely to default than South, which is more likely to default than North East

Less important than the top 5 features but I wanted to mention that 

6.	__DTI (Debt to Income Ratio)__ is important for many credit rating agencies and banks, but it's not on top important feature in my model
    - a.	DTI is the ratio of how much debt a borrower has relative to their income
    - b.        Log Annual income is more important than DTI
    - c.	Since income is what services the debt, a higher DTI ratio would result in higher likelihood of charge offs, but income is still more important


7.	__Purpose__
    - a.	A category provided by the borrower for the loan request. 
    - b.	Credit Card is the reason most people take out a loan from the Lending Club, followed by Debt Consolidation


### Results
<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/new/xgb5/feat_chart.png" >
<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/new/xgb5/feat_imp.png" >








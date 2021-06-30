# Classification : Loan Repayment Prediction

# Project Proposal


## Question

The purpose of the model I plan to build is to predict whether an individual borrower will repay their loan (or not) given various data points and information from a historical database. 

So in the future, when we have a new potential borrower coming to us, we can predict if this person will pay back or not. This will help with the decision making framework for whethe to lend to the borrower or not.


My client, a lending institution, provides loans to the borrower and charges interest. The borrower is obligate to pay interest periodically, but also pay back the full principal of the loan at the end. If the borrower repays the loan, the lender will receive the full interest rate and their initial capital they loaned. If the borrower defaults at any point in time, the lender would lose the entire principal of the loan as well as interest payments not yet received. This would be a large impact to the lender's profit and capital base.  

With this prediction model, my client will benefit from being able to predict the risk of the borrower on whether they will pay back the loan and interest or not.

Lowering the risk of borrower defaults using the model, the lender will face a lower % of its borrowers defaulting and thus help the business to earn higher profits and maintain more customer relationships.


## Data

#### 	Resource  : Kaggle
This dataset is provide by [Lending Club](https://www.lendingclub.com) and it’s downloaded from Kaggle.


1.	[Lending Club 2007-2020Q3](https://www.kaggle.com/ethon0426/lending-club-20072020q1?select=Loan_status_2007-2020Q3.gzip)

	It's a large dataset ( 2,925,493 datapoints with 150+ features) so I plan to cut down the size and only use the most recently 5 years data for my analysis.

	__Features including:__
	- Variables: 

		loan amount, employee title, employee length, home ownership, annual income, debt to income ratio, loan purpose, FICO, loan grades from Lending Club, interest rate, installments, address state, etc.

	- Target: 

		Loan Status, whether Charged Off or Fully Paid, will be the target I aim to predict.



2.	[Loan Dictionary](https://www.kaggle.com/ethon0426/lending-club-20072020q1?select=LCDataDictionary.xlsx)
      
      It’s a detailed descriptions table for all features/columns from the dataset. See below for some examples:


<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/LoanDictionary.png">



## Tools
#### Classification - sklearn
1. modeling
    * from sklearn.model_selection import train_test_split
    * from sklearn.preprocessing import StandardScaler
    * from sklearn.linear_model import Logisticregression
    * from sklearn.tree import DecisionTreeClassifier 
    * from sklearn.ensemble import RandomForestClassifier
	* from sklearn.neighbors import KNeighborsClassifier
	* from sklearn.metrics import roc_auc_score
2. evaluation
	* from sklearn.metrics import classification_report,confusion_matrix

#### Data cleaning & analysis 	
	
* import numpy as np
* import pandas as pd

#### Visualizations	
1. pairplot
    * import matplotlib.pyplot as plt  	%matplotlib inline
      
2. mapping
    * Tableau




## MVP Goal:

✨Ａ histogram to show the relationship between Interest Rate and Loan Status(repay or default)✨

✨Ａ data visualization chart from Tableau to see which states have more borrowers default on loan.✨

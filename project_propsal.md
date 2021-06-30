# Project 4 Classification : Loan Repayment Prediction

# Project Proposal


## Question

The purpose of the model I plan to build is to predict whether this individual borrower will repay the loan (or not) given the certain information from historical database. 

So in the future, when we have a new potential borrower/customer coming to us, we can predict if this person will pay back or not, then it can help the decision making for lending out the loan or not. /we can decide if we should lend out the loan.


My client, bank loan department/ lending institution, provides loans to the borrowers with charging interest rate. If the borrower repays the loan, the lender can gain the profit with interests. If not/the opposite/the borrower cant payback, the lender would lose money from the borrower failed to repay and it can hurt the business.  

With this prediction model, my client will benefit from being able to predict the risk of the borrower on whether they can repay or not.

As lowering the risk of borrower not paying back by using this model, the lender will have less exposure on borrowers default and money loss, by not only helping the department making decisions easier and better, but also gaining profits on the higher chance


## Data

#### 	Resource  : Kaggle
This dataset is provide by [Lending Club](https://www.lendingclub.com) and it’s downloaded from Kaggle.


1.	[Lending Club 2007-2020Q3](https://www.kaggle.com/ethon0426/lending-club-20072020q1?select=Loan_status_2007-2020Q3.gzip)

	It's a large dataset ( 2,925,493 datapoints with 150+ features) so I plan to cut down the size and only use the most recently 5 years data for my analysis.

	__Features including:__
	- Variables: 

		loan amount, employee title, employee length, home ownership, annual income, debt to income ratio, loan purpose, FICO, loan grades from Lending Club, interest rate, installments and address state

	- Target: 

		Loan Status, as whether is charged off or fully paid, will be the target I want to predict if the borrower will repay the loan or default.



2.	[Loan Dictionary](https://www.kaggle.com/ethon0426/lending-club-20072020q1?select=LCDataDictionary.xlsx)
      
      As below, it’s a detailed descriptions table for the data features/columns 


<img src="https://github.com/SYNYC/2_Project_Movies/blob/main/charts/df%20head.png">



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

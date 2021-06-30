# Project 4 Classification Project : Loan Repayment Prediction

# Project Proposal


## Question

o	The purpose of the model I plan to build is to predict whether this individual borrower will repay the loan (or not) given the certain information from historical database.
o	 So in the future, when we have a new potential borrower/customer coming to us, we can predict if this person will pay back or not, then it can help the decision making for lending out the loan or not. /we can decide if we should lend out the loan.


o	My client, bank loan department/ lending institution, provides loans to the borrowers with charging interest rate. If the borrower repays the loan, the lender can gain the profit with interests. If not/the opposite/the borrower cant payback, the lender would lose money from the borrower failed to repay and it can hurt the business.  
o	
o	With this prediction model, my client will benefit from being able to predict the risk of the borrower on whether they can repay or not.
o	
o	As lowering the risk of borrower not paying back by using this model, the lender will have less exposure on borrowers default and money loss, by not only helping the department making decisions easier and better, but also gaining profits on the higher chance


## Data


o	This dataset is provide by [Lending Club](https://www.lendingclub.com) and it’s downloaded from Kaggle.
o	
o	
###	Resource  : Kaggle
1.	[Lending Club 2007-2020Q3](https://www.kaggle.com/ethon0426/lending-club-20072020q1?select=Loan_status_2007-2020Q3.gzip)
It's a large dataset ( 2,925,493 datapoints with 150+ features) so I plan to cut down the size and only use the most recently 5 years data for my analysis 

#### Features including
- Variables: 
loan amount/employee title/employee length/home ownership/annual income/debt to income ratio/loan purpose/FICO/loan grades from Lending Club/interest rate/installments/address state

- Target: 
Loan Status , as whether is charged off or fully paid, will be the target I want to predict if the borrower will repay the loan or default.



2.	[Loan Dictionary](https://www.kaggle.com/ethon0426/lending-club-20072020q1?select=LCDataDictionary.xlsx)
As below, it’s a detailed descriptions table for the data features/columns 


<img src="https://github.com/SYNYC/2_Project_Movies/blob/main/charts/df%20head.png">



## Tools
##### Classification
- sklearn
    * from bs4 import BeautifulSoup
    

## MVP Goal:

✨A data visualization chart to help to identify the correlations between variables.✨

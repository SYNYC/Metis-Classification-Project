# MVP
##### Sabrina Yang


Initially I had almost 3 million data points and 140 features. I aimed to get to a smaller size of  dataset with less than 50 features to process my next step.


<class 'pandas.core.frame.DataFrame'>
RangeIndex: 2925493 entries, 0 to 2925492
Columns: 141 entries, id to debt_settlement_flag
dtypes: float64(106), object(35)
memory usage: 3.1+ GB ''' 


After doing data cleaning, EDA and feature engineering, I was able to cut down to 246,000 data points with 28 features. Here’s what I did:



1. drop the columns have missing values more than 30 % -> cut down to 104 features

2. check the Loan Dictionary for each columns definition and decided to drop or not -> cut down to 51 features

3. delete the row with missing values -> n size : 2925493 to 2657654

4. made a histogram on loan issued date and found out most of the records are between 2017 to 2020, I assumed Lending Club is getting popular overtime, so I only took recent 3 years loan data : 2018 Jan to 2020 Sep  -> n : 246004

5. drop financial institution features as interest rate, grade, sub grade, fico score since these are likely created by financial professionals and I’d like to see my model perform without it first. Later I might add it back to see if it will improve my model since they are good predictors. 


6. the relationship between feature "employment length' and target "Loan Status. Borrowers with 10+ year employment length tend to pay back their loan the most. On the other hand, it's also the majority group who charged off the loan.

 <img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/employ_length.png">

7. create dummies for Catergorical features and applied feature engineer on "address state" - break into 4 major US regions instead of each state.
 
 
8. made a pairplot to observe the trend on numeric features. 

<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/pairplot.png" width = "1000" height = "1000">



## Baseline Model - Simple Logistic Regression


I ran a simple Logistic Regression as my baseline model. In my project, I assume banks don't want to lend out money to borrowers who can’t pay back, so I will focus more on Recall than Precision. However, my baseline model Recall is only 0.02, but I’ll improve on my next model.
Baseline model F1 score is 0.042. Test AUC: 0.626. See the following for Classification Report and Confusion Matrix: 



<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/logreg_report.png" > 



 <img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/confusion_matrix_logreg.png">




## Logistic Regression with Oversampling

As I making “Charged Off” on loan as positive class (1) and “Fully Paid” as negative class (0), the ratio is imbalance (2:8), so I added Weighted Class for Oversampling method to balance it. The scores improved: Recall increased to 0.53, F1 score is 0.42. Test AUC: 0.626.  See the following for Classification Report and Confusion Matrix: 



<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/logreg_oversampling_report.png">


<img src="https://github.com/SYNYC/4_Project_Loan_Repayment/blob/main/charts/confusion_matrix_logreg_oversampling.png">





## Next 
I plan to use Random Forest and XGBoost for more modeling.  






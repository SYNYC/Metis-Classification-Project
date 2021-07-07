# MVP
##### Sabrina Yang


Initially I had almost 3 million data points and 140 features . I aimed to get to a smaller size of  dataset with less than 50 features to process my next step.


After doing data cleaning, EDA and feature engineering, I was able to cut down to 246,000 data points with 28 features. Here’s what I did:



1. drop the columns have missing values more than 30 % -> cut down to 104 features

2. check the Loan Dictionary for each columns definition and decided to drop or not -> cut down to 51 features

3. delete the row with missing values -> n size : 2925493 to 2657654

4. made a histogram on loan issued date and found out most of the records are between 2017 to 2020, I assumed Lending Club is getting popular overtime, so I only took recent 3 years loan data : 2018 Jan to 2020 Sep  -> n : 246004

5. drop financial institution features as interest rate, grade, sub grade, fico score since these are likely created by financial professionals and I’d like to see my model perform without it first. Later I might add it back to see if it will improve my model since they are good predictors. 

6. made a pairplot to observe the trend on numeric features. It doesn't provide much insights on which features are more outstanding.


<img src="https://github.com/SYNYC/3_Project_EV/blob/main/charts/AADT.png">

   width = "750" height = "450">


## Baseline Model - Simple Logistic Regression


I ran a simple Logistic Regression as my baseline model. In my project, I assume banks don't want to lend out money to borrowers who can’t pay back, so I will focus more on Recall than Precision. However, my baseline model Recall is only 0.02, but I’ll improve on my next model.
Baseline model F1 score is 0.042. Test AUC: 0.626. See the following charts for more details:


Classification Report
<img src="https://github.com/SYNYC/3_Project_EV/blob/main/charts/AADT.png">


Confusion Matrix
 <img src="https://github.com/SYNYC/3_Project_EV/blob/main/charts/AADT.png" width = "750" height = "450">




## Logistic Regression with Oversampling

As I making “Charged Off” on loan as positive class (1) and “Fully Paid” as negative class (0), the ratio is imbalance (2:8), so I added Weighted Class for Oversampling method to balance it. The scores improved: Recall increased to 0.53, F1 score is 0.42. Test AUC: 0.626. 


Classification Report
<img src="https://github.com/SYNYC/3_Project_EV/blob/main/charts/AADT.png">


Confusion Matrix
<img src="https://github.com/SYNYC/3_Project_EV/blob/main/charts/Final_Ranking.png" width = "850" height = "450">





Next, I plan to use Random Forest and XGBoost for more modeling.  






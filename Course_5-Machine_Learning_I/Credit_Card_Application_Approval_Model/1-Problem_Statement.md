# Problem Statement

You have reached the end of the course on Machine learning I, which covered inferential statistics and hypothesis testing, linear regression, and logistic regression. It is now time to apply these concepts. In the next video, Ankit will explain the business scenario and the problem statement that you need to solve in this assignment.

**VIDEO**

## Problem Statement

An MNC financial organisation operates in multiple geographies in various product segments (liabilities as well as credit). In the past few years, the bank has been on an expansion spree. As part of this expansion drive, it is looking to grow its customer base who purchase credit products. So, the bank is looking to push credit cards to new customers in one of the markets in which it is operating. Now, since this market is not mature in terms of data governance and reporting, the credit bureau (such as CIBIL and Experian) does not have data on all the existing card customers.

In order to expand its credit card portfolio, the bank is looking to build a credit card application approval model. Normally, banks process credit card applications based on credit bureau scores. Since this market does not have a credit bureau score for the majority of the customers, building such an application approval model becomes tricky. As the bank has some presence in the credit card space in the region, the data available to build the model contains the application data and performance of these customers. For a good understanding of the data set, you can go through the data description given below.

## Data Understanding

As explained by Ankit, you have two data sets, which are as follows: 

1.  **Credit card application:** This contains the demographic information of the users who are applying for the credit card. 
    
2.  **Credit card performance:** This contains the performance of the users after they are issued the credit card.
    

Download [Data Dictionary](Data_Dictionary.xslx)


**Note:** The current date of when the data is extracted is considered a starting point, which is why you will find records with negative values under the Days_birth, Days_Employed and Months_balance columns.

## Target Variable

As you must have observed in the problem statement, your task is to build a credit card approval model that predicts whether a customer's credit card is delinquent or not, solely based on the customer's application data.

Now, let's understand what the term delinquency means. **Credit card delinquency** occurs when a cardholder falls behind on making the required monthly payments. Typically, a customer's credit card is considered delinquent if they have delayed the minimum payment by more than 30 days.

In this assignment, you are required to use the credit card performance data to create the target variable, i.e., whether the customer's credit card is delinquent or not. **The user ID will be classified as delinquent if the customer has ever delayed their payment by more than 60 days.**

## Steps Involved

Let’s watch the next video to learn about the steps involved in this assignment.

**VIDEO**

Let's go over the steps explained by Ankit in the video above:

1.  The data set lies in AWS S3, so you need to connect to S3 and read the data to a Spark data frame. You can find the data set in the following public S3 links or locally through this GitHub repo:
    
    - [https://s3.amazonaws.com/sqoop.oozie.ml/credit_record.csv](https://s3.amazonaws.com/sqoop.oozie.ml/credit_record.csv)
        
    - [https://s3.amazonaws.com/sqoop.oozie.ml/application_record.csv](https://s3.amazonaws.com/sqoop.oozie.ml/application_record.csv)
		
	- [Credit and Application Records ](Credit_and_Application_Records.zip)
        
2.  Once the data is successfully loaded, perform EDA (Exploratory data analysis) on it to understand the data set and use well-considered visualisations to unwrap the insights. (You may use Python libraries for any necessary plots and visualisations).
    
3.  Perform any required checks such as variable exploration, outlier treatment, missing value imputation, variable transformation and correlation check.
    
4.  Apply the concepts of Weight of Evidence and Information Value to perform variable exploration and variable transformations. (You will learn more about these concepts in the next segment.) 
    
5.  Once the data preprocessing is complete, build a credit card application approval model.
    
6.  Fine-tune the model and then evaluate the model by considering various metrics such as precision, recall, F1-score, AUC score and KS statistic, and finally, create a small write-up to explain the different model tuning techniques that you have applied and the details of the performance of the model in each scenario.
    

**As part of the EDA, report your observations for the following questions:**

1.  What is the proportion of females in the applicant customer base?
    
2.  Is homeownership higher among male applicants or female applicants?
    
3.  Is there any correlation between the customer's income level and education level?
    
4.  What is the average and median salary of the applicant base?
    
5.  Is the proportion of bad customers higher for people who own cars?
    
6.  Is the proportion of bad customers higher for those living on rent than the rest of the population?
    
7.  Is the proportion of bad customers higher for those who are single than married customers?
    

**Important Note**

The results and inferences can be submitted in a separate report explaining your inferences at each step.

#### Data Understanding

Qn: Import the credit_record data set, and select the correct options about the user 5001711 (first ID in the data set) from below. (Note: More than one option may be correct.)

- The customer has not taken any loan for the current month.

- The customer has paid the loan for the past three months and not taken any loan in the current month.

- The customer has defaulted by 1-29 days in the past four months.

- The customer has defaulted by 1-29 days in the past three months.

Ans: A & D.

- *The first statement is true because for month 0, the status is marked as X, which means that the customer has not taken any loan.*

- *The second statement is correct, as the status of the customer for the past three months has been shown as 0, which implies that the customer has defaulted each of these months by 1-29 days.*

#### Data Understanding

Qn: Considering the defined customer credit card delinquency, is the customer ID 5001711 a delinquent customer?

- Yes

- No

Ans: B. *The customer's credit card is considered delinquent if the customer has defaulted in making the payment at any point for more than 60 days. In this case, although the customer has defaulted by 1-29 days for each of the three months, they have not yet crossed the 60-day mark. In other words, they have paid the loans for each of the three months within 29 days. Hence, this customer is not a delinquent customer.*

## Additional Links

You can learn about credit card delinquency from the following link.

Investopedia: [Credit Card Delinquency](https://www.investopedia.com/articles/pf/11/intro-to-credit-card-delinquency.asp#:~:text=Credit%20card%20delinquency%20occurs%20when,reported%20to%20credit%20reporting%20agencies.)

In the next segment, you will develop an understanding of the two important concepts that are widely used in the banking industry: Weight of Evidence and Information Value.
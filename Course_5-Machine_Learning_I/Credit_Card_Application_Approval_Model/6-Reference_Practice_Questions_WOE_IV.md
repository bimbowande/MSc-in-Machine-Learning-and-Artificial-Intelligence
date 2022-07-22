# Practice Questions: WOE — IV

## Comprehension 1

You are required to **download the data set** from below in order to answer the questions.

Download [Tenure Contract WOE Data](Tenure_WOE_Data.xlsx)

In the attached file, you will find three sheets. The first sheet contains three variables (Tenure, Contract and Churn) from the telecom data. The second sheet contains the distribution of the binned tenure variable. The third sheet contains the distribution of goods and bad information about the contract variable.

With this information, attempt the questions given below.

#### WOE Analysis

Qn: What information would you infer from the WOE trend of the Tenure variable?

- As tenure increases, the chances of churning decrease.

- As tenure increases, the chances of churning increase.

- As tenure decreases, the chances of churning decrease.

Ans: A. *If you calculate the WOE value of all the 10 buckets, you will notice that as tenure increases from 1 year to 72 years, the WOE values also increase continuously from -1.46 to 2.12. Thus, it decreases the chances of churning over the bucket.*

Qn: Select the correct option from below.

- Coarse binning is required for the Tenure variable, as there is no monotonic trend in fine binning.

- Coarse binning is not required for the Tenure variable, as there is a clear monotonic trend in fine binning.

Ans:B. *If you create a plot out of the WOE value, you will be able to clearly visualise a monotonic plot.*

Qn: What does a negative WOE signify in the Contract variable (refer sheet-3)?

- The percentage of churners (bad customers) is more than the percentage of no-churners (good customers).

- The percentage of churners (bad customers) is less than the percentage of no-churners (good customers).

- The percentage of churners (bad customers) is equal to the percentage of no-churners (good customers).

- Cannot say

Ans: A. *The WOE is expressed by ln (percentage of non-churns in bucket/ percentage of churns in the bucket). If the WOE is negative, it means that the percentage of churns in that bucket is greater than the percentage of non-churns in that bucket.*

Qn: Compare the WOE trends of the variables Tenure and Contract.

Considering the WOE trend, which variable, when increased in value, will decrease the likelihood of churn?

- Tenure

- Contract

- Both

- None of the above

Ans: C. *The variable Tenure as well as the variable Contract both negatively impact the churn rate over the buckets. This means that if the Tenure variable increases, the churn rate decreases and vice versa. Similarly, for the Contract variable, the two-year contract has a lower chance of churn than the one-year contract.*

#### Information Value

Qn: What is the total information value of both the variables?

- Contract = 0.83, Tenure = 1.24

- Contract = 1.24 , Tenure = 0.83

- Contract = 0.83, Tenure = 1.29

- Contact = 1.29, Tenure = 0.83

Ans: B. *Information Value for each bucket can be calculated as follows: IVbucket = WOEbucket * (% good - % bad ) Total IV for Tenure = IVbucket-1(0-1) + IVbucket-2(2-5) + IVbucket-3(6-11)+IVbucket-4(12-19) + IVbucket-5(20-28) + IVbucket-1(29-39) + IVbucket-2(40-49) + IVbucket-3(50-59)+IVbucket-4(60-68) + IVbucket-5(69-72) Total IV for Tenure = 0.23+0.12+0.02+0.01+0.00+0.01+0.02+0.05+0.12+0.26 = 0.83 Total IV for Contract = IVbucket-1(month-to-month) + IVbucket-2(One-year) + IVbucket-3(two-year) Total IV for Contract = 0.33+0.17+0.74 = 1.24*

Qn: Select the correct option from below.

- The Contract variable has a stronger predictive power than the Tenure variable.

- The Contract variable has a weaker predictive power than the Tenure variable.

- Both variables show the same predictive power.

- Cannot say anything

Ans: A. *Predictive power can be measured based on information values. So, higher the information value, higher is the predictive power. In this example, the Contract variable shows an IV of 1.24 and the Tenure variable shows an IV of 0.83.*

## Comprehension 2

Consider the data set given in the Excel sheet below.

Download [Grade WOE Data](Grade_WOE_Data.xslx)

**Note**: You are required to download the attached Excel file in order to answer the questions. This file contains two sheets. The first sheet contains observation or data entries of two variables,'Loan status' and 'Grade'. And, the second sheet contains the distribution of goods and bad buckets for the 'Grade' variable.

#### Questions

Qn: What do you infer from the WOE plot of the Grade variable?

- As the loan grade varies from A to G, the WOE values gradually decrease from +0.99 to -1.09.

- As the loan grade varies from A to G, the WOE values gradually increase from -0.99 to +1.09.

- As the loan grade varies from A to G, WOE values gradually decrease from -0.99 to -1.09.

- As the loan grade varies from A to G, the WOE values gradually increase from +0.99 to +1.09.

Ans: A. *The WOE values for each bucket are as follows: A = 0.99, B = 0.21, C = -0.20, D = -0.50, E = -0.77, F = -1.04 and G = -1.09. All the values starting from A to G gradually decrease from +0.99 to -1.09.*

Qn: Select the correct option from below.

- The WOE graph shows monotonic nature.

- The WOE graph does not show monotonic nature.

- All the grade categories show positive WOE values.

- All the grade categories show negative WOE values.

Ans: A. *Based on the WOE value, you can clearly visualise a monotonic plot.*

Qn: Fill in the blank. "The information value of the Grade variable is \_\_\_\_\_."

- 0.56

- 0.43

- 0.34

- -0.23

Ans: C. *The information value for each bucket can be calculated as follows:*

*IVbucket = WOEbucket * (% good - % bad )*

*Total IV for the Grade variable = IVbucket-1(A) + IVbucket-2(B) + IVbucket-3(C)+ IVbucket-4(D) + IVbucket-5(E)+ IVbucket-4(F) + IVbucket-5(G)*

*Total IV for grade variable = 0.18 + 0.01 + 0.01 + 0.04 + 0.05+0.04+0.01 = 0.34*

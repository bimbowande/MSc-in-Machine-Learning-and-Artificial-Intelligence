# Graded Questions

All the best!

## Problem Statement 1:

Consider the following statements:

1. John (aged 29 years) earns Rs. 6 Lakhs per annum and has an average monthly balance of Rs 18000. He plans to repay the loan in 8 years time.

2. Chris (aged 52 years) earns Rs. 8 Lakhs per annum and has an average monthly balance of Rs. 38000. He plans to repay the loan in 18 years time. 

The loan application of John is rejected, while that of Chris is accepted. 

Keeping this in mind, answer the questions that follow:

![Loan Eligibility](https://i.ibb.co/t2nNvQG/Loan-Eligibility.png)

#### Interpreting a decision tree

Qn: From the options given above, which decision tree would correctly predict whether John and Chris's loan applications would be accepted or rejected?

- A

- B

- C

- D

Ans: A. *John's age is less than 50 years, income is less than 8 Lakhs per annum, average monthly balance is less than 2000 and repayment tenure is less than 20 years. As per these conditions, Tree A and Tree C reject his application. Further, Chris's age is greater than 50 years, average monthly balance is less than 40000 and repayment tenure is less than 20 years. As per these conditions, out of Tree A and Tree C, Tree A accepts his application.*

Qn: An applicant aged 32 years, earns Rs 10 Lakhs per annum and has an average monthly balance of Rs. 18000. He plans to repay the loan in 25 years. As evident from the correct decision tree chosen previously, the applicant's loan application is accepted. 

Which of the following changes in the applicant's details would, however, make him ineligible for the loan?

- If average monthly balance was Rs 16000

- If income of the applicant was Rs. 9 Lakhs per annum

- If age of the applicant was 52 years 

- If repayment tenure of the applicant was 15 years.

Ans: C. *If the applicant's age was 52 years, the model would check the average monthly balance. Since the average monthly balance is less than 40000, the model would check the repayment tenure. The applicant's repayment tenure is greater than 20 years. Thus, the model would reject his application.*

## Problem Statement 2:

Let’s take another look at the artificial data set and answer the questions based on the data provided. The table shown below shows the number of individuals that play or do not play football based on their Gender and Age. Take a look at the table below:

| Gender/Age | Age < 50          | Age > 50          |
|------------|-------------------|-------------------|
| Female     | P - 10<br>N - 390 | P - 0<br>N - 100  |
| Male       | P - 250<br>N - 50 | P - 50<br>N - 150 |

where,   
P implies ‘plays football’ - class A = label 1.  
N implies ‘does not play football’ - class B = label 2.

#### Homogeneity

Qn: Calculate the homogeneity of the given source data set using the entropy measure.

- 1

- 0.89317

- 0.70556

- 0.53241

Ans: B. *You can calculate the homogeneity as follows:*  
$P(play) = 310/1000$ ; $P(don't play)  = 690/1000$ 

$Homogeneity=−P(play)log_2P(play)−P(don′t\ play)log_2P(don′t\ play)$

$Homogeneity=−(310/1000)log_2(310/1000)−(690/1000)log_2(690/1000)=0.89317$

#### Information Gain

Qn: What is the information gain of the partitions if you split on ‘gender’?

- 0.3369

- 0.5502

- 0.8931

- 0.4633

Ans: A. *Calculate the entropy of the original data set, and subtract the entropy of the partitions obtained after splitting on gender:  Information gain $= 0.8931-0.5562 = 0.3369$*

#### Splitting Criteria

Qn: You can calculate the information gain for both if we split on “Age” or on “Gender”.  What attribute should you split the original data on?

- Gender 

- Age

Ans: A. *You split on the attribute that maximises the information gain. The information gain on gender is greater than the information gain on age.*
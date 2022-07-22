# Evaluation Metric: KS Statistic

Let's watch the next video to learn about an important metric used extensively in the context of predictive modelling. 

**VIDEO**

**Note**: At 2:32, when Ankit explains the table, the column names for goods and bads have been interchanged, whereas the column values remain the same. Please ignore this mistake.

KS measures the discriminatory power of the model by considering the maximum difference between the cumulative goods and bads.

The steps involved in calculating KS are as follows:

1.  Score the data set using the model and create a column containing the predicted probabilities.
2.  Sort (high to low) the probability column and create ten bins containing equal observations.
3.  For each bin, calculate the goods, the bads, the cumulative goods, the cumulative bads, the percentage of cumulative goods and the percentage of cumulative bads.
4.  For each decile, take the difference between the percentage of cumulative goods and the percentage of cumulative bads. The maximum value of this new column is the KS as shown below:

![KS Statistic](https://i.ibb.co/xHtW63B/KS-Statistic.png)

## Comprehension

Use the Churn Analysis data set provided below to calculate the KS statistic. Note that the data has already been segregated into deciles.

Download [Churn Analysis Question](Churn_Analysis_KS_Statistic.xlsx)

Calculate the KS statistic for the Churn Analysis.

#### KS Statistic

Qn: Find the value of the KS statistic.

- 48.1%

- 52.8%

- 33.9%

- 74%

Ans: 

Now that you have understood the concept of KS Statistic, let's watch the next video to learn about the various evaluation metrics that you need to submit for this assignment.

**VIDEO**

The evaluation metrics that you need to report are as follows: 

1. KS Statistic
2. AUC 
3. Confusion Matrix (Precision, recall, F1-score)

Note that since this is a highly imbalanced data set, you will face difficulty in achieving both high precision and high recall. So, it is recommended that you mainly focus on a **higher recall** while not suffering precision too much, as the bank is mainly interested in identify the defaulters. As mentioned previously, credit card default could be considered a fraud; hence, it is important that we correctly classify all default cases to minimise risks and losses.

In the next segment, you will get an idea of the evaluation rubrics which will be used to evaluate your submission.
# Weight of Evidence and Information Value

In this segment, you will gain an understanding of the concepts of Weight of Evidence (WOE) and Information Value (IV), which are used extensively in predictive modelling. You will learn more about these concepts during our discussion on IV and WOE.

Let’s watch the upcoming video to learn about WOE.

**VIDEO**

As you learnt in the video above, Weight of Evidence indicates the predictive power of the independent variable in relation to the dependent variable.

**Steps to Calculate WOE:** 

1.  Divide the variable in n equal bins
    
    1.  Continuous variable: In the case of continuous variables, you will have to divide the variable's values into n bins.
        
    2.  Categorical variable: In categorical variables, since each value belongs to a discrete category, each category becomes a bin.
        
2.  For each bin, calculate the number of events and non-events, and then, calculate the percentage of the event (goods) and the percentage of the non-event (bads).
    
3.  Calculate the WOE using the following equations:
     $$WOE = ln\left(\dfrac{good\ in\ the\ bucket}{Total\  Good}\right)−ln\left(\dfrac{bad\ in\ the\ bucket}{Total\ bad}\right)$$
    
    Or  
    $$WOE=ln\left(\dfrac{Percentage\ of\ Good}{Percentage\ of\ Bad}\right)=ln\left(\dfrac{Percentage\ of\ Event}{Percentage\ of\ Non−Event}\right)$$
    
#### Important Note:

1.  While dividing the variable into bins, each bin should have at least 5% of observations.
2.  The WOE should be monotonic (increasing or decreasing).  
    Once you have calculated the WOE values, they should follow an **increasing or decreasing trend** across bins. If the trend is not **monotonic**, then you will need to compress the buckets or bins (coarse buckets) of that variable, and then, calculate the WOE values again.

**Note**: To check for monotonicity, you can use the spearman correlation coefficient or a metric of your own. The details about this correlation are provided in the optional session.

### Benefits of WOE

1.  The **WOE reflects group identity**, which means that it captures the general trend of distribution of good and bad customers.  
    Example: The difference between customers with 30% credit card utilisation and 45% credit card utilisation is not the same as the difference between customers with 45% credit card utilisation and customers with 60% credit card utilisation. This is captured by transforming the variable 'credit card utilisation' using the WOE.
2.  It **can handle outliers,** as it involves creating a separate bin for outliers.
3.  It **can handle missing values,** as this set of records is considered a different category while binning the records.
4.  It **can handle categorical variables**. So, you need not create dummy variables, which prevents our input feature vector from becoming sparse.
5.  It helps you **create a linear relationship with a log of odds**. 

Let’s watch the next video to learn about the pros and cons of WOE transformation from Hindol.

**VIDEO**

The pros and cons of the WOE transformation are as follows:

1.  **Pros**: The model becomes more stable because small changes in the continuous variables will not impact the input so much.
2.  **Cons**: You may end up doing some score clumping.

This is because when you are using WOE values in your model, you are doing something similar to creating dummy variables; you are replacing a range of values with an indicative variable. Instead of replacing it with a simple 1 or 0, which was not thought out at all, you are replacing it with a thought-out WOE value. Hence, the chances of undesired score clumping is a lot less here.

Let's watch the next video to understand another important concept known as Information Value.

**VIDEO**

As you learnt in the video above, I**nformation Value** can be calculated using the following expressions:
$$IV=\sum WOE∗ \left(\dfrac{\text{Good in the bucket}}{\text{Total Good}}−\dfrac{\text{Bad in the Bucket}}{\text{Total Bad}}\right)$$

or
$$IV=\sum WOE ∗\left(\text{Percentage of good in the bucket}−\text{Percentage of bad in the bucket}\right)$$
This is an important indicator of **predictive power**.

Mainly, this helps you understand how the binning of variables should be done. The binning should be done such that the WOE trend across the bins is monotonic, either increasing all the time or decreasing all the time. 

In the next video, you will learn about the usual thresholds that are followed in the banking sector. Note that these thresholds may vary from sector to sector.

**VIDEO**

**Important Note**

While calculating the IV values, you may end up getting very low values, which means that all the features available are weak predictors. In the actual industry scenario, you will have a lot more information available to boost the predictive power of a feature, but **for this assignment, you can try the modelling exercise using the available weak predictors.** **You can use a threshold of 0.002 after calculating the IV values to eliminate the weak predictors.**

You can try to attempt the practice questions provided in the optional segment. Please note that the Python code has not been provided anywhere, and as part of this assignment, you are required to develop your own code and perform the feature transformation.

## **Additional Links**

[Weight of Evidence and Information Value Explained](https://www.listendata.com/2015/03/weight-of-evidence-woe-and-information.html)

[Replacing Variables by WoE (Weight of Evidence) in Logistic Regression](https://stats.stackexchange.com/questions/189568/replacing-variables-by-woe-weight-of-evidence-in-logistic-regression)

[Kaggle: WOE and IV](https://www.kaggle.com/emotionevil/category-features-selection-information-value)

[Medium: WOE and IV](https://medium.com/@sundarstyles89/weight-of-evidence-and-information-value-using-python-6f05072e83eb)

Use the table given below to answer the next question.

![Credit Card Application Case Study Qn Table](https://i.ibb.co/k67sVYj/Cred-Application-Case-Study-Qn-Table.png)

#### WOE and IV Calculation

Qn: Calculate the following:

1. WOE for gender = male

2. IV for gender = male

- WOE (Male) = 0.404; IV = 0.219

- WOE (Male) = 0.204; IV = 0.019

- WOE (Male) = 0.324; IV = 0.149

- WOE (Male) = 0.544; IV = 0.239

Ans: B. 
$$WOE=ln\dfrac{\% Event}{\% Non-Event}=ln\dfrac{45/88}{5/12}\approx0.204$$
$$IV=WOE*(\text{\% Event}-\text{\% Non-event})=0.204*(0.511-0.416)\approx0.019$$
In the next segment, you will learn an important metric known as the **KS (Kolmogorov–Smirnov) statistic**, which is used extensively in the context of predictive modelling.
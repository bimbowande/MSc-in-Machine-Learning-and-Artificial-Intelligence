# Model Comparison: Telecom Churn Prediction

In this segment, you will learn how decision trees and random forests compare against logistic regression. We will look at the telecom churn prediction example, which we considered in the module on logistic regression. You will use the same data set with the same problem statement and build the tree models to learn how they are better than the logistic regression model. But before you start, please go through the data set and the previous Python notebook and recall the initial steps of data cleaning and preparation for building the model. 

**Problem Statement**  
A telecom firm has collected data on all of its customers. The main types of attributes include the following:

-   Demographics (age, gender, etc.)
-   Services availed (internet packs purchased, special offers taken, etc.)
-   Expenses (e.g., amount of recharge done per month)

Based on this past information, you want to build a model that would predict whether a particular customer would churn or not, i.e., whether they would switch to a different service provider. So, the variable of interest, i.e., the target variable here is ‘Churn’, which would indicate whether or not a particular customer has churned. It is a binary variable, where 1 means the customer has churned and 0 means the customer has not churned.

You can download the data sets from the links given below.

Download [churn_data](churn_data.csv)

Download [internet_data](internet_data.csv)

Download [customer_data](customer_data.csv)

The data dictionary is attached below.

Download [Telecom Churn Data Dictionary](Telecom_Churn_Data_Dictionary.csv)

You can also download the code file given below and follow along. Do not worry if the code provided in the file below does not match the video for some sections as the older functions are no longer supported on all machines.

Download[ Telecom Churn Case Study Notebook](Telecom_Churn_Logistic_DT_RF.ipynb)

Before using the tree models to solve the problem, let us try to revisit the results obtained in the logistic regression model. 

**VIDEO**

You will notice that the model did a decent job in predicting whether a person is going to churn or not.

In the forthcoming video, you will learn how to build decision trees over the same data set and understand the trade-offs, benefits and limitations of decision trees as compared with logistic regression.

**VIDEO**

#### Hyperparameter Tuning

Qn: How do these hyperparameters help to control the limitations of the decision tree model?

Ans: *These two hyperparameters restrict the model from overfishing. Using a lower value for depth and higher value for min_samples_leaf reduces the overfitting in the model.*

In the video, without putting much effort into scaling, multicollinearity, p-values and feature selection, you obtained impressive and better results using decision trees than using a logistic regression model. However, remember that decision trees are high-variance models and that they change quite rapidly with small changes in the training data. In such a case, you either prune the tree to reduce the variance or use an ensemble method, such as random forest. In the next video, you will learn how random forests can help you stack better than both logistic regression and decision tree models against this prediction problem.

**VIDEO**

#### Feature Importance

Qn: Which is the most important feature according to the random forest model? Does this align with the results of the logistic regression model?

- Tenure, Yes

- TotalCharges

- Tenure, No

- InternetService_No, Yes

Ans: C. *The coefficient of tenure has an absolute value of 1.56 in the logistic regression model, which is lower than the absolute value for InternetService_No (1.69).*

Random forests certainly produced great improvement in the results with much less effort as compared with both logistic regression and decision trees. It has exploited the predictive power of decision trees and has learnt much more than a single decision tree could alone. However, there is not much visibility with respect to the key features and the direction of their effects on the prediction, which is done well by a logistic regression model. If interpretation is not of key significance, then random forests certainly do a great job.

#### Tree Hyperparameters

Qn: You have learnt that one of the hyperparameters to limit the growth of a decision tree is the depth of the tree. Which of the following are some other hyperparameters to limit the growth of a tree? (More than one option can be correct.)

- Random state

- The minimum number of samples required to split an internal node

- The minimum number of samples to be present at a leaf node

- The splitting criteria

Ans: B & C. *The hyperparameter, `min_samples_split`, limits the split of an internal node, thus restricting the growth of the tree. The hyperparameter, `min_samples_leaf`, limits the split of an internal node if it finds that the leaf nodes originating from that internal node do not satisfy the mentioned criteria, thus restricting the growth of the tree.*

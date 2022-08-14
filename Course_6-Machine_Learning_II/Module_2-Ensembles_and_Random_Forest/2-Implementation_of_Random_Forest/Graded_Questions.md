# Graded Questions

Now that you have completed the session, answer the questions given below to test your understanding of the concepts covered.

All the best!

#### Feature Importance

Qn: How do you calculate feature importance in random forests for a particular attribute?

- We select the best-performing tree in the random forest and calculate the feature importance from that tree.

- We take an attribute and check all the trees in which it was present, and then check in which of the trees is the change in the homogeneity on this attribute split the highest. This highest value of the change in the homogeneity gives us the feature importance of that attribute.

- We take an attribute and check all the trees in which it was present, and take the average values of the change in the homogeneity on this attribute split. This weighted average value of the change in the homogeneity gives us the feature importance of that attribute.

- The total number of trees in which an attribute is present divided by the total number of trees gives us the feature importance of that attribute.

Ans: C. *Recall that we take all the trees in which an attribute was present and aggregate the homogeneity measures to calculate feature importance. We basically select all the trees in which an attribute was present and calculate the ΔHomogeneity on the attribute split. We then take a weighted average of all of these ΔHomogeneity in order to arrive at the final feature importance.*

#### Random Forest

Qn: From the statements below, choose the correct ones. (More than one option may be correct.)

- The value for the attribute ‘n_estimators’ should always be kept very high (in 1,000s) while building a random forest model. This is because model performance improves with the increase in the number of trees.

- It is better to build base decision trees in the random forest model with a few attributes for each split, instead of including most of them.

- Assuming a good accuracy score for all the models, the random forest is a better model than logistic regression or decision trees if you want both robustness and interpretability from the model.

- The training time for the random forest model does NOT depend upon the bootstrap method.

Ans: B. *It makes the trees more diverse because attributes lower the chances of feature dominance in the model.*

## Bank Marketing Data Set

You are provided the bank marketing data set, which contains data on a telemarketing campaign run by a bank to sell a product (term deposit: a type of investment product).

The sample contains different attributes, which have been preprocessed for you. In this question, you will build multiple random forest models and compare their performance.

**Description of Data Set**  
Each row represents a ‘prospect’ to whom phone calls were made to sell the product. There are various attributes describing the prospects, such as age, profession, education level and previous loans taken by the person. Finally, the target variable is ‘purchased’ (1/0); 1 indicates that the person had purchased the product.

You can download the data set from the link given below.

Download [marketing_churn](bank_sample.csv)

Follow the instructions provided and select the correct answers:

-   Keep the random state or seed value as 42 for standardisation at all times. Answers associated with other values will not be accepted
-   Training set (70%) and test set (30%) (the random state for the train–test split is also 42)

#### Model Performance: Accuracy

Qn: How does the random forest model perform when it is built without any feature engineering using the following hyperparameters:

-   bootstrap=True
-   criterion='gini'
-   max_depth=3
-   n_estimators=10
-   oob_score=True
-   random_state=42

Use accuracy as the performance metric.

- The model performs well on both the training and test sets. Performance on the test set is better than that on the training set.

- The model performs poorly on both the training and test sets. Performance on the training set is better than that on the test set.

- The model performs well on the training set but poorly on the test set.

- The model performs well on the test set but poorly on the training set.

Ans: A. 

*Train Accuracy : 0.9032957502168256*

*Test Accuracy : 0.9110212335692619*

*Based on accuracy, the model performs well on both the training and test sets.*

#### Model Performance: OOB Score

Qn: What is the range in which the OOB score of the model prepared in Question 1 lies?

- 0.75–0.84

- 0.85–0.94

- 0.95–1

- 0.65–0.74

Ans: B. *rf.oob_score_ gives the OOB score of the model. Here, the value comes out to be ~0.89.*

#### Model Performance: Ideal Metric

Qn: Which metric would serve the best judgement on the results of the model?

**Hint:** You want to cover as many actual conversions as you can and, at the same time, not waste a lot of time and money calling customers.

- Accuracy

- Precision

- Recall

- F-score

Ans: D. *Since you want to cover as many actual conversions as you can, recall needs to be high; at the same time, as you do not want to waste a lot of time and money calling customers, the predictions should cover as many positives. Hence, precision should also be good. This suggests that the F-score should be considered, which involves both precision and recall.*

#### Model Building: GridSearch

Qn: What is the value of the F-score on the test set?

- 0.84–0.95

- 0.14–0.25

- 0.24–0.35

- 0.64–0.75

- 0.54–0.65

Ans: C. 

```python
from sklearn.metrics import f1_score

f1_score(y_test, rf.predict(X_test))
```

*The above code will give you a value of approximately 0.28 which lies in the given range.*

#### Feature Importance

Qn: Based on the model created, which is the most important feature in determining whether a customer would purchase the policy or not?

- age

- previous

- euribor3m

- duration

Ans: D. *This feature has an importance score of 0.29, which is the maximum among all the other values.*
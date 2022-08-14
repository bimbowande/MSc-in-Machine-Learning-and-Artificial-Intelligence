# Regression: Housing Price Prediction - II

In the previous segment, you performed a basic exploration of the data set. Now, in this segment, you will prepare the data for applying the random forest regressor. Similar to multiple linear regression, the data needs to be numerical here as well. Hence, you will start by performing dummy encoding on the categorical variables as shown in this video.

**VIDEO**

So, in the video, you learnt how to convert all the yes/no variables into 1/0. However, the ‘furnishing status’ feature is a non-binary categorical variable. Hence, we will use the dummy variable method to convert this feature into a numeric feature as shown in the video below.

**VIDEO**

The values in the categorical variables with two levels have been replaced with 1 and 0. However, in the case of furnishing status, the variable had three levels, so you need to perform dummy encoding using pd.get_dummies with the condition drop_first = True. You then drop the original column ‘furnishingstatus’ as you have already processed it and no longer need it.

So, now that we have converted all the features into the numerical format, in the next video, we will split the data into train and test data.

**VIDEO**

Here, we have performed a 70:30 split, but it was not necessary. Do you remember why? Since the amount of data is less, we could have estimated the model performance using the OOB error.

Although scaling is not essential in tree models, scaling of variables can be helpful. As you may have noticed, the variable ‘area’ is on a different scale compared with all the other numerical variables, which take smaller values. Also, the categorical variables that you encoded earlier take either 0 or 1 as their value. Hence, it is good to have everything on the same scale for the model to be easily interpretable.

#### Scaling

Qn: Why do we scale features in linear and logistic regression as opposed to decision trees or random forests?

- In linear and logistic regression, to see the importance of variable, you look at the coefficient values; hence, to have a comparison, all the features should be on the same scale. In the case of decision trees or random forests, feature importance is calculated in a different manner, as you have seen in the previous segment, and scaling does not make a difference.

- It is also necessary to perform scaling in trees in order to look at feature importance.

Ans: A.

Now that you have prepared the data and have completed the test–train split, everything is ready for building the random forest model. Here, you will use the RandomForestRegressor(), instead of the classifier, which was used in the heart disease prediction problem. 

Before proceeding to build the model, you must also create the X_train, y_train, X_test and y_test as shown below.

```python
# Train and test sets
y_train = df_train.pop("price")
X_train = df_train

y_test = df_test.pop("price")
X_test = df_test
```

Now, let us create a model using some hyperparameters for the demonstration of regression using a random forest. You can perform hyperparameter tuning as we did earlier.

**VIDEO**

So, as you saw in the video, the random forest model does not produce excellent results on both the training and testing data sets. However, this does not mean that the random forest model cannot be used for this problem. As an exercise, you can perform more hyperparameter tuning here and improve the performance of the model that you built right now.

Regarding feature importances, the results show that ‘area’ is the most crucial variable in predicting house prices, which is intuitive. The other features that are given below may not be intuitive, and this is how a variable’s importance helps with identifying the correct features. Another advantage is that if you need to build a more intuitive linear regression model, because the business has demanded it, then you would not eliminate these variables with high feature importance during feature selection in linear regression. You can also go through the implementation of the linear regression model for the same problem, as the code has been provided to you.

#### Hyperparameters

Qn: You have seen that we have set the following hyperparameters to implement the random forest regressor:

1.  n_estimators
2.  random_state
3.  max_depth
4.  min_samples_leaf

Which other hyperparameters can be tuned?

- min_samples_split

- min_impurity_decrease

- criterion

- max_features

Ans:  All the above.

#### random_state

Qn: How does setting the random_state help?

Ans: *Since a random forest involves two random processes, data bootstrapping and random feature selection, the results can vary significantly as you re-run the model. Hence, to minimise this and replicate the results, you set the random_state to a particular value.*

You now have three different models to solve both regression and classification problems:

-   Linear/logistic regression
-   Decision trees
-   Random forest

In the next segment, we will try to fit all the three models on a classification problem and check their performance.
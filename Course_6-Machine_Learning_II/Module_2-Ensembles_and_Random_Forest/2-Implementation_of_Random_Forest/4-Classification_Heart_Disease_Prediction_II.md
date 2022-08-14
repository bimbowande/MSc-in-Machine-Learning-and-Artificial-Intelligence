# Classification: Heart Disease Prediction - II

In the previous segment, you learnt how to build a random forest classifier and look at the individual estimator within them. In the forthcoming video, we will perform some hyperparameter tuning using gridsearchcv().

**VIDEO**

#### n_estimators

You have received the best model with the following attributes in the model:

```python
RandomForestClassifier(bootstrap=True, class_weight=None, criterion='gini',
            max_depth=5, max_features=3, max_leaf_nodes=None,
            min_impurity_decrease=0.0, min_impurity_split=None,
            min_samples_leaf=5, min_samples_split=2,
            min_weight_fraction_leaf=0.0, n_estimators=30, n_jobs=-1,
            oob_score=False, random_state=42, verbose=0, warm_start=False)
```

It has been mentioned before that the random forest model improves with the increase in the number of trees in the forest. However, the number of trees is restricted to 30 in this case even when it could go till 100. What will happen to the model accuracy if we increase the number of trees to 50? Give the accuracy value for the revised model.

- Model accuracy reduces to 0.6-0.7 on the test data.

- Model accuracy increases to 0.85 on the test data.

- Model accuracy remains unchanged.

Ans: A. *Accuracy of the model decreases because the dataset is too small to create a set of diverse bootstrapped samples. This reduces the diversity in the model and hence, the accuracy value of the model reduces. You can experiment over this by repeating the exercise after defining a smaller ratio for bootstrapped samples.*

As you can see, hyperparameter tuning can result in drastic improvements to the model. The model accuracy has increased to 80% after we used the hyperparameters below.

![RF Best](https://i.ibb.co/DbZZQ4p/RF-Best.jpg)

#### GridSearchCV

Consider that we use the following params to tune the random forest model:

```python
params = {  
    'max_depth': [2, 3, 5, 10],  
    'min_samples_leaf': [5, 10, 20, 50],  
    'criterion': ["gini", "entropy"]  
    'n_estimators': [30, 50, 100]  
}
```

Also, the params are passed on as shown below:

```python
grid_search = GridSearchCV(estimator=dt,   
                           param_grid=params,   
                           cv=5, n_jobs=-1, verbose=1, scoring = "accuracy")
```

Qn: What is the search space to find the best random forest model?

- 5

- 96

- 100

- 480

Ans: B. *Search space is the number of hyperparameter combinations that can be tried in order to find the best set of hyperparameters, which is 4 x 4 x 2 x 3  = 96.*

Qn: What is the number of random forest models that would be created in order to search for the best random forest model?

- 96

- 1

- 480

- 5

Ans: A. *There will be 96 random forest models built for each fold.*

So, now that we have a good model, the next step is to understand its intricacies. The next video will help you understand the notion of variable importance in random forests through Python.

**VIDEO**

The attribute ‘age’ contributes the maximum to the decision of whether a person has heart disease or not.

![RF Heart Disease Params](https://i.ibb.co/wcbgXRY/RF-Heart-Disease-Params.jpg)

To summarise, in this segment, you learnt how to build a random forest in sklearn. Apart from the hyperparameters that you have in a decision tree, there are two more hyperparameters in random forests: **max_features** and **n_estimators**. The effects of both the hyperparameters are briefly summarised here:

-   **max_features:** This feature helps you decide the number of attributes that the algorithm would consider when the splitting criteria are checked. You learnt that there is an optimal value of max_features, i.e., at extremely low values, the component trees are quite simple to learn anything useful, whereas at extremely high values, the component trees become similar to each other (and violate the ‘diversity’ criterion).
-   **n_estimators:** This defines the number of decision trees that you would have in the random forest. If you can plot and observe the relationship between n_estimators and the training and test accuracies, then you would notice that as you increase the value of n_estimators, the accuracy of both the training and test sets gradually increases. More importantly, the model does not overfit even when its complexity is increasing. This is an important benefit of random forests but is only true when you have a data set that is large enough. You can increase the number of trees as much as you like without worrying about overfitting (only if your computational resources allow). 

Now, try answering the question below to test your understanding.

#### Random Forest - Hyperparameter max_features

The hyperparameter max_features specifies the maximum number of features that is considered at each node’s split. For example, if the data set contains 25 features and you specify max_features = 4, then at each split (in the component trees), only a maximum of 4 randomly chosen features would be considered. 

According to you, how would the ensemble performance vary as you gradually increase the value of max_features? Compare your guess with that of your batchmates.

At very low values of max_features (e.g., 2), both training and test accuracy will be low; both training and test accuracy would gradually increase with max_features up to a certain point. However, at extremely high values (e.g., 19), both will decrease again.

At very low values of max_features (e.g., 2), both training and test accuracy will be high; both training and test accuracy would gradually reduce with max_features down to a certain point. However, at extremely high values (e.g., 19), both will increase again.

At very low values of max_features (e.g., 2), both training and test accuracy will be low; both training and test accuracy would gradually increase with max_features up to a certain point. However, at extremely high values (e.g., 19), training accuracy would continue to increase, whereas test accuracy will reduce (thus, the model would overfit).

Attempt 0 of 1

Submit

In the next segment, you will learn how to fit a random forest model on a continuous target variable.
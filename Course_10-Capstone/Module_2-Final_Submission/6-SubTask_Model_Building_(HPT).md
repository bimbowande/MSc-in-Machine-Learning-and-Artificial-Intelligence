# SubTask: Model Building (HPT)

In the next video, Arihant will explain the model creation process and the significance of Scenario 1 and Scenario 2 in detail.

**VIDEO**

In the video above, Arihant explained the models that you have to build for the Capstone Project. While building your models, you may come across two different scenarios for which you will have to create separate models. These scenarios are as follows:

-   **Scenario 1**: You have all the data present (i.e., you have the latitude-longitude data, application id data, event data and devices data).
-   **Scenario 2**: For some device ids, you may only have the mobile phone, brand and device data available.

So, for both these scenarios, you may want to create two separate models. Let's take a look at these now.

**Scenario 1**

In this scenario, you need to create two models, one for gender prediction (binary classification) and the other for age prediction (regression or multiclass classification). In the case of the gender prediction problem, you need to build a logistic regression model to benchmark your model and an XG boost model using GridSearch, followed by the stacking classifier.

For the age prediction model, you can choose between a regression model or a classification model. You can use age as a continuous variable and build a regression model or convert the age variable into discrete bins (such as [0-24, 25-32, 32+]), thereby converting the problem into a multiclassification problem.

**Note**: You must provide proper reasoning regarding the type of model you want to build, Regression or Classification.

If you choose to build the regression model, you will have to use linear regression, followed by the XG boost model and finally the stacking regressor. You will learn about the stacking regressor in detail in the next few videos. If you want to build the model as a multiclass classification model, you will have to develop a logistic regression model, followed by an XG Boost classifier and a stacking classifier. 

**Scenario 2**

Now, you are left with only the mobile phone-related device information, i.e., mobile phone brand and model. So, you have to perform gender prediction and age prediction for the same. The framework and algorithms to be used in this scenario are precisely the same as those in Scenario 1, the only difference being the data set.

In the next video, Arihant will explain the hyperparameters that you need to consider while building an XGBoost classifier as part of the model-building exercise.

**VIDEO**

As you saw in the video on model building, you will have to create an XGBoost classifier, followed by GridSearch for both the scenarios. Now, XGBoost takes in several parameters, and these parameters need to be optimised in order to achieve the best results for the algorithm. This process of optimising the learning parameters is known as **Hyperparameter Tuning**.

So, essentially, in the machine learning context, hyperparameter tuning refers to the problem of choosing a set of optimal hyperparameters for a learning algorithm.

Let's come back to the XGBoost model and take a look at the parameters of the XGBoost algorithm, which are as follows:

1.  **max_depth**: This parameter signifies the maximum depth of the tree. Increasing this value will make the model more complex and more likely to overfit. For this, the default value is 6.
2.  **subsample**: This parameter indicates the ratio of the sample to its training instances. When you set this to 0.5, the XGBoost model will randomly sample half of the training data before growing trees, which will prevent overfitting. Subsampling will occur once in every boosting iteration. For this, the default value is 1.
3.  **eta**: This is the rate at which the model is trying to learn so that we can reach the global minima. For this, the default value is 0.3.
4.  **n_estimators**: This is the number of trees that need to be produced.
5.  **gamma**: A node is split only when the resulting split gives a positive reduction in the loss function. This parameter specifies the minimum loss reduction required to do a split.
6.  **min_child_weight**: This parameter defines the minimum sum of weights of all observations required in a child node. It is used for controlling overfitting. 
7.  **colsample_bytree**: This parameter denotes the fraction of columns that need to be randomly sampled for each tree. For this, the default value is 1.

So, for the hyperparameter tuning of the XGBoost model, you can use the GridSearch CV function of the sklearn library, as shown below.

```python
from sklearn.model_selection import GridSearchCV

# A parameter grid for XGBoost

params = {

        'min_child_weight': [1, 5, 10],

        'gamma': [0.5, 1, 1.5, 2, 5],

        'subsample': [0.6, 0.8, 1.0],

        'colsample_by_tree': [0.6, 0.8, 1.0],

        'max_depth': [3, 4, 5],

        'n_estimators': range(60, 360, 40),

        'learning_rate': [0.1, 0.01, 0.05]

 }
```

You will have to perform Hyperparameter Tuning (HPT) for Scenario 1 and Scenario 2 for both age prediction as well as gender prediction.

In the next segment, you will learn about Stacking models, which you will have to implement as part of the model-building exercise.
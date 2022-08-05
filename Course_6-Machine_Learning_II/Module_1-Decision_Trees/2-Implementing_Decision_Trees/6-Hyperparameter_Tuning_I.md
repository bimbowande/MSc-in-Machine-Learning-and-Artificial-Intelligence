# Hyperparameter Tuning - I

How do you control the complexity (or size) of a tree? A very ‘big’ or complex tree will result in overfitting. On the other hand, if you build a relatively small tree, it may not be able to achieve a good enough accuracy (i.e., it will underfit). In order to avoid overfitting, you can use hyperparameters, which you learnt about in the previous segment. So, what values of hyperparameters should you choose? 

Hyperparameters are the choices that the algorithm designer makes to ‘tune’ the behaviour of the learning algorithm. The choice of hyperparameters, therefore, has a lot of bearing on the final model produced by the learning algorithm.  

So, anything that is passed on to the algorithm before it begins its training or learning process, is a hyperparameter, i.e., the parameter that the user provides, and not something that the algorithm learns on its own during the training process. Here, one of the hyperparameters you can input is "max_depth", which essentially determines how many levels of nodes will you have from root to leaf. This is something that the algorithm is incapable of determining on its own and has to be provided by the user. Hence, it is a hyperparameter.

Now, as hyperparameters can take many values, it is essential for you to determine the optimal values where the model will perform the best. This process of optimising the hyperparameters is called hyperparameter tuning. 

You will be using the same dataset that you used earlier to predict whether the person has a heart disease or not. Let’s take a look at the next video where Sajan will explain how to find the optimal value of the max_depth hyperparameter:

**VIDEO**

#### Parameters

Qn: What do you know about the max_depth parameter?

Ans: *Following are the benefits of max_depth parameter:*
1.  *max_depth refers to the maximum depth of the tree.*
2.  *Its default value is None.*
3.  *We can prune the tree by defining the max_depth hyperparameter.*
4.  *The tree becomes easy to visualise.*

**Cross-validation** is a statistical approach where you divide the dataset into train and test dataset for estimating the best model. The test data serves the purpose of unseen data on which the model fits after training on the train dataset. You have already seen this earlier. One of the demerits of cross-validation is that sometimes the split can be biased, specifically in case of limited data and the difference between the train and test dataset can be such that we are not able to build a satisfactory model. Hence, in such cases, k-fold cross-validation helps in finding the best model.

k-fold cross-validation is a resampling process to validate the model. In the k-fold cross-validation process, the data is divided into k subsets of data. Hence, if you have 1000 data points and if k=10, it forms a 10-fold cross-validation model. Therefore, each fold will have 100 data points. Now, we build k models, each model corresponding to the kth fold in the test set and the rest of the k-1 folds as the training set. The final predictions are the average value of the k models that you build for a particular set of parameters. In this way, you ensure that the bias between the train and test dataset upon split is not there. You can refer [here](https://scikit-learn.org/stable/modules/cross_validation.html) to read more about cross-validation. In the demonstration, Sajan has used n_folds instead of k. 

Now, let’s take a look at the code given below in order to implement the max_depth parameter:

```python
# Import the libraries required:
from sklearn.model_selection import KFold
from sklearn.model_selection import GridSearchCV

# Define the parameters
parameters = {'max_depth': range(1,10)}

# You can define the number of folds for cross-validation as follows:
n_folds = 5

# Using the following code, call the decision tree classifier method:
dtree = DecisionTreeClassifier(criterion='gini', random_state=0)

# Use GridSearchCV to implement max_depth as follows:
tree=GridSearchCV(dtree,parameters,cv=n_folds,scoring="accuracy",return_train_score=True)

# Fit the training data in the Decision Tree as follows:
tree.fit(x_train, y_train)

# You can view the results as follows:
scores = tree2.cv_results_

# Plot the training and testing data accuracy as follows:
plt.figure
plt.plot(scores["param_max_depth"].data,scores["mean_train_score"],label="training_accuracy")
plt.plot(scores["param_max_depth"].data, scores["mean_test_score"], label="test_accuracy")
plt.xlabel("max_depth")
plt.ylabel("accuracy")
plt.legend()
plt.show()
```

Now,  in the upcoming video, Sajan will show you how to implement the min_sample_leaf parameter: 

**VIDEO**

Let’s take a look at the code given below in order to implement the min_samples_leaf parameter:

```python
# Define the parameters as follows:
parameters = {'min_samples_leaf': range(10,200,20)}

# Use GridSearchCV to implement max_depth as follows:
tree= GridSearchCV(dtree, parameters, cv=n_folds, scoring="accuracy",return_train_score=True)
```

The remaining code is the same as the one given above in the case of max_depth. You saw how the tree tends to overfit at high values of max_depth and low values of min_samples_leaf. Note that decision trees are notorious for overfitting; they can achieve 100% training accuracy if they are allowed to grow too deep (while the test accuracy is of course quite lesser).

In the next segment, we'll continue the process of hyperparameter tuning.  
 

## Additional Reading:

1.  To learn more about the difference between [Parameters and Hyperparameters](https://www.hitechnectar.com/blogs/hyperparameter-vs-parameter/)
# Hyperparameter Tuning - II

Until now, you were working with the individual effects of hyperparameters to understand how they affect the resulting tree. Now, let's find the optimal combination of the hyperparameters. Instead of using one parameter at a time, you can tune your Decision Tree for multiple parameters at once using max_features. In the upcoming video, Sajan will show you how to implement it:

**VIDEO**

#### Score

Qn: How is the mean_train_score calculated?

Ans: *k models are built on each of the kth fold as the test data and the accuracy score is calculated for the k models denoted by split0_train_score, split1_train_score and so on. The mean_train_score is the mean of the above scores for the k different models built. Note that this score may be different from accuracy which can also be decided before training.*

You can find out the most suitable parameters using grid.best_params_ and the best accuracy score using the grid.best_score_ function.  
   
Let’s now watch the next video to see how to create a tree that is easy to visualise and understandable by a common person.

**VIDEO**

The final Decision Tree will look like the one given in the image shown below:

![Final Decision Tree Heart Disease](https://i.ibb.co/nw3fbX0/Final-Decision-Tree-Heart-Disease.png)

In this image, you can easily visualise the tree to understand whether a person has heart disease or not. However,  changing the hyperparameters of a Decision Tree affects its accuracy. Let’s now compare the tree models you have already created above with and without hyperparameters and compare their confusion matrix. Let’s take a look at the next video where Sajan will explain you the confusion matrix for different Decision Tree models:

**VIDEO**

The code to find out the confusion matrix is as follows:

print(classification_report(y_test, y_preds2))

For a better understanding of the model, you can also plot the ROC curve as follows:

```python
# Import the required libraries:
import matplotlib.pyplot as plt  
import sklearn.metrics as metrics

# Define false and true positive rate as follows:
fpr, tpr, thresholds=metrics.roc_curve(y_test,y_preds1) 

# Plot the ROC curve:
plt.plot(fpr,tpr)
plt.plot([0, 1], [0, 1], color='darkblue', linestyle='--')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic (ROC) Curve')
plt.show()
```
You can take a look at the ROC curve given below before and after using hyperparameters:

![ROC Curves Before and After](https://i.ibb.co/WkZDVhd/ROC-Curves-Before-After.png)

The area under the ROC curve increases with hyperparameter tuning showing the improvement in the performance of the model.

#### True/False

Qn: State whether the following statement is true or false. "The min_samples_split parameter specifies the minimum number of data points required in a node to be considered for further splitting."

- True

- False

Ans: A. *As mentioned in the documentation, the min_samples_split parameter specifies the minimum number of data points required in a node to be considered for further splitting.*

#### Decision Tree Hyperparameters

Qn: Choose the correct option from those given below.  "As you increase the value of the min_samples_leaf hyperparameter, the resulting tree will:"

- become more complex, and can potentially overfit the data 

- become less complex, and the depth will tend to reduce.

- not be different from a tree with a lower value of min_samples_leaf.

Ans: B. *The min_samples_leaf parameter specifies the minimum number of samples required in a (resulting) leaf for the split to happen. Thus, if you specify a high value of min_samples_leaf, the tree will be forced to stop splitting quite early.*

So far, you have implemented Decision Trees using Python. In the next segment, you will implement case studies using PySpark.
# Graded Questions

All the best!

## Comprehension - Hyperparameters

Consider a decision tree classification model that has a high training accuracy and a low test accuracy, i.e., the model has a high variance. The training accuracy is 98%, and the test accuracy is 55%. The ‘min_samples_split’ for this model is 5, 'min_samples_leaf' is 3 and the ‘max_depth’ is 20.

Now, answer the following questions:

#### Hyperparameters

Qn: What does the ‘min_samples_split = 5’ imply? (Note: More than one option may be correct.)

- The minimum number of samples required to split an internal node is equal to 5.

- Even if a node has 5 samples, it can be further divided into leaf nodes.

- A node cannot be split if the number of samples is equal to 5.

Ans: A & B. *The hyperparameter min_samples_split is the minimum number of samples required to split an internal node. Its default value is 2, which means that even if a node has 2 samples, it can be further divided into leaf nodes.*

Qn: Suppose you decide to tweak the hyperparameters so as to decrease the variance/overfitting. Which of the following steps will help? (Note: More than one option may be correct.)

- Increasing min_samples_split

- Decreasing  min_samples_split

- Increasing max_depth

- Decreasing max_depth

Ans: A & D. 

- *A low value of the min_samples_split will lead to a small number of data points in the nodes. This means that it is likely that each leaf (obtained after splitting) is going to represent very few (or only one, in some cases) data points. This, in turn, means that tree depth increases and we intend to reduce the tree depth.*

- *Decreasing max_depth will stop the tree to grow deeper. That way, your tree will not overfit the data and you will have a decent accuracy in both test and train.*

Qn: What will be the (likely) impact of increasing the value of min_samples_leaf from 3 to 4?

- The depth will decrease.

- The depth will increase.

Ans: A. *As the leaf should now contain at least 4 data points, it'll restrict some of the internal nodes to not split further and hence decreasing the depth of the tree.*

## Comprehension - Python Implementation

You will be required to build a tree to predict the income of a given population, which is labelled as <= 50K and >50K. The attributes (predictors) are age, working-class type, marital status, gender, race, etc. Download the dataset and Python notebook given below:

Download [Dataset](adult_dataset.csv)

Download [Notebook](Graded_Question_Notebook.ipynb)

You will first require to clean the dataset and then prepare the data in a format which sklearn can understand using string indexer/one-hot encoder/vector indexer as per requirement. The Jupyter Notebook provided above contains instructions and directions for completing the case study and answering the following questions:

#### Comprehension

Qn: What is the accuracy of the basic model built without any hyperparameter tuning?(Select the most appropriate range). Use random_state = 27.

- 0.75-0.85

- 0.86-0.90

- 0.91-0.95

- 0.65-0.74

Ans: A *Use the following code to print the accuracy after building the Decision Tree:*

```python
print(accuracy_score(y_test,y_pred_default))
```

What is the change in accuracy after using hyperparameters defined according to the below param_grid? (select the range which your answer satisfies)

```python
param_grid = {  
    'max_depth': range(5, 15, 5),  
    'min_samples_leaf': range(50, 150, 50),  
    'min_samples_split': range(50, 150, 50),  
    'criterion': ["entropy", "gini"]  
}
```

Use random_state = 27

- 0.21 - 0.3

- 0.11 - 0.2

- 0-0.1

- Does not improve

Ans: C. *Change in accuracy = Accuracy(hyperparameter) - Accuracy(initial)  
Change in accuracy = ~0.85 - ~0.80 = ~0.05*

# Overfitting and Pruning

In the previous segment, you saw that due to the huge size of the tree, it was difficult to visualise the tree properly. When you construct such a deep tree with a huge amount of data and try to classify the entire training data, you may end up classifying the data you have trained on correctly. But when you use the same model on a test data, the accuracy may drastically reduce. Such a condition is referred to as overfitting. Take a look at the upcoming video, where Sajan will explain about overfitting and how to deal with it:

**VIDEO**

Earlier, you saw that decision trees have a strong tendency to overfit the data, which is a serious problem. So, you have to keep an eye on the size of the tree. A huge tree will have one leaf only to cater to a single data point which is not required. Hence, there are two broad strategies to control overfitting in decision trees:

1.  **Truncation:** Stop the tree while it is still growing, so that it may not end up with leaves containing very few data points. Truncation is also referred to as pre-pruning. 
2.  **Pruning:** Let the tree grow to any depth. Then, cut the branches of the tree in a bottom-up fashion, starting from the leaves. This is also known as post-pruning, i.e pruning the tree after it has grown.

In the next video, Sajan will explain the pruning techniques in detail:

**VIDEO**

Pre-pruning or early-stopping is a method of stopping a Decision Tree to grow before it overfits. In case of pre-pruning/ truncation, the tree is pruned back up to the point where the cross-validation error is minimum. On the other hand, post-pruning involves chopping the branches of a Decision Tree created from the entire data available. In this case, the tree is pruned slightly further than the minimum error point. These methods increase test accuracy by reducing overfitting.

  
Pre-pruning is generally preferred over post-pruning because it is less rigorous, resource-intensive and saves time. Also, it is more practical to stop the tree at a feasible point rather than create the whole tree and then chop it off. Take a look at the tree shown in the image given below:

![Decision Tree Pruning](https://i.ibb.co/FnCKKRh/Decision-Tree-Pruning.png)

  
This image shows the tree ‘before’ pruning and the tree ‘after’ pruning. The red dots belong to the class ‘Label 1’ and the blue dots belong to the class ‘Label 2’. Now, answer the following questions based on the image given above:

#### Pruning

Qn: How many observations/data points will the new leaf have?

- 16

- 12

- 8

- 4

Ans: C. *The observations in the leaf will be the same as before. Suppose you have 4 observations in the node and you split it such that the left partition has 1 observation and the right partition has 3 observations. Now, if you chop these partitions, then the original node, which is now a leaf, will still have 4 observations.*

Qn: Which label will be assigned to the new leaf?

- Label 1

- Label 2

Ans: A. *In the leaf, as the number of points that belong to label 1 is greater than those that belong to label 2, label 1 will be assigned to it.*

Qn: If the test accuracy after pruning the unseen data decreases significantly, then:

- You should prune the branch.

- You should not prune the branch.

Ans: B. *You should prune the branch only if the test accuracy does not decrease after pruning.*

The DecisionTreeClassifier function in sklearn provides the following hyperparameters, which you can control in order to prune your trees:

-   criterion (Gini/IG or entropy): It defines the function to measure the quality of a split. Sklearn supports “gini” criteria for the Gini Index and “entropy” for the Information Gain. By default, it takes the value “gini”.  
     
-   max_features: It defines the number of features to be considered while looking for the best split. You can input integer, float, string and None values.
    -   If an integer is an input type, then it considers that value as max features at each split.
    -   If a float value is taken, then max_features is a fraction and int(max_features * n_features) features are considered at each split.
    -   If “auto” or “sqrt” is taken, then max_features=sqrt(n_features).
    -   If “log2” is taken, then max_features= log2(n_features).
    -   If None, then max_features=n_features. By default, it takes “None” value.  
         
-   max_depth: It denotes the maximum depth of a tree. It can take any integer value or None value. If it takes None value, then nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples. By default, it takes “None” value.  
     
-   min_samples_split: It denotes the minimum number of samples required to split an internal node. If an integer value is taken, then consider min_samples_split as the minimum number. If a float value is taken, then it shows the percentage. By default, it takes the “2” value.  
     
-   min_samples_leaf: It denotes the minimum number of samples required to be at a leaf node. If an integer value is taken, then consider - -min_samples_leaf as the minimum number. If a float value is taken, then it shows the percentage. By default, it takes the “1” value.

There are other hyperparameters in the DecisionTreeClassifier function as well. You can read the documentation in Python using: 

```python
help(DecisionTreeClassifier)
```

#### Truncation and Pruning

Qn: The process of splitting when there is a sufficient number of data points in the node is called \_\_\_\_\_.

- Truncation

- Pruning

Ans: A. *Truncation lets you split the data only when the number of data points in the node is greater than or equal to the 'minsplit'.*

Qn: Which of the following hyperparameters controls the minimum number of samples required to split an internal node?

- min_samples_split

- max_depth

- min_samples_leaf

- max_features

Ans: A. *This parameter specifies the minimum number of data points a node should have for it to be considered for splitting.*

Qn: \_\_\_\_\_ takes care of the minimum number of samples required to be present at a leaf node.

- min_samples_split

- min_samples_leaf

- max_features

- max_depth

Ans: B. *This parameter denotes the minimum number of samples required to be at a leaf node. If an integer value is taken, then consider - -min_samples_leaf as the minimum number. If a float value is taken, then it shows the percentage. By default, it takes the “1” value.*

Qn: Assume that you have set the min_samples_leaf as 3 and the min_samples_split as 6. Consider a node with 10 data points. On splitting on an attribute, one leaf gets 2 points, and the other gets 8 data points. This split will not be executed. Why?

- The number of data points in the node is greater than min_samples_split.

- The number of data points in one of the leaves is smaller than  min_samples_leaf.

- The number of data points in one of the leaves is greater than min_samples_leaf.

- The number of data points in the node is greater than min_samples_leaf.

Ans: B. *The number of data points in one of the leaves is 2, which violates the condition that the number of data points in a leaf should be at least 3 (as specified by the min_samples_leaf).*

#### Truncation

Qn: In the below 'Tree after pruning' which is pruned using the truncation method, what all can be values for min_samples_split?

![Decision Tree Pruning](https://i.ibb.co/FnCKKRh/Decision-Tree-Pruning.png)

- 4

- 8

- 9

- 14

- 12

Ans: C, D & E. *The number of points 8 in the right node should be less than the min_samples_split. In other words, min_samples_split > 8.*

You will come across a coding example in Python in the next segment, where Sajan will show you how these hyperparameters affect the structure of the tree.

## Additional Reading:

1.  Refer to the link to learn how to implement [Pruning](https://stackoverflow.com/questions/39002230/possible-to-modify-prune-learned-trees-in-scikit-learn) in Python.
2.  Refer to this link to learn more about different [hyperparameters](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html).
# Chicago Crime Case Study - VII

In the previous segments, you have completed all the pre-processing steps and, now, it is time to build the model on the processed data. As learnt before, you should first split the data into training and test sets in a 70:30 ratio. In the next video, Sajan will explain more on the next steps.

**VIDEO**

As you saw in the video, here is a summary of all the steps in the process of the model building:

1.  We began by considering a train-test split in the ratio 70:30 and the seed as 100. This was done using the randomSplit() function of PySpark.
    
2.  Since this is a classification problem, we will use the RandomForestClassifier to train the random forest model. The hyperparameters for the model have been kept as numTrees = 25, maxDepth = 5 and impurity = 'gini'. You must also provide the seed value (100 in this case) to fix the bootstrapped samples.
    
3.  Finally, we fit the model over the training set using the fit() function.
    

Now, let's try to apply the model on the testing set and evaluate its performance.

**VIDEO**

As you can see in the video, we have obtained the predictions from the model under the ‘predictions’ variable after transforming the test data. After that, we evaluated the model by computing the accuracy using the MulticlassClassificationEvaluator.

In the next video, you will learn how different variables contribute to the recommendation of the FBI code through feature importance.

**VIDEO**

The results show that 'Primary Type_encoded_BATTERY' is the most crucial variable in predicting house prices. Here, you may see that the results are not the same as SkLearn library. This is because the ML library takes input in the form of vectors. Therefore, the feature importance is computed for each vector instead of the variable.

By now, you have learnt how to rank features based on their importance for the RF model in Spark environment. Let's summarise the steps that were executed in the videos you saw earlier:

-   Once the model is fit on the training set, we predict the target variable on the testing set and print the label, predictions and probabilities.
    
-   Since there are more than two target labels, we must use the MulticlassClassificationEvaluator and compute the accuracy and the test error.
    
-   As you can see, the model provides 81% accuracy on the test set. However, it was iterated previously that the classification model should not be gauged only with the accuracy metric. This becomes even more important when more than one class is to be predicted. You should check the performance of the model for each class to decide whether the model is satisfactory or not.
    

 In the next segment, you will learn how to optimise the entire process in Spark.
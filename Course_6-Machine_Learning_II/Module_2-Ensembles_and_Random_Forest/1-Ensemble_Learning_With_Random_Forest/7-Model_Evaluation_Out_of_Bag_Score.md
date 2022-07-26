# Model Evaluation: Out-of-Bag Score

In the previous segment, you went through all the steps of building a random forest model. The next step in the process of model building is model validation. In this regard, the random forest has yet another feature known as out-of-bag error that helps you in choosing the best model. Hence, it does not require you to divide the data into training and validation/test data.

In the next video, you will get a detailed understanding of the evaluation process.

**VIDEO**

Generally, for evaluating a machine learning model, we split the data set into training and test data. However, it is not essential in the case of the random forest algorithm. The base models in the algorithm are built on a subset of the training data. Hence, the entire data is automatically divided into the following two parts: a training set and a validation set. Thus, it omits the need for set-aside test data. However, you can still keep part of the data as the testing set to test the model on unseen data.

The validation set consists of all the data points that were not used by the base model to train the tree. These are termed as **out-of-bag (OOB)** samples for the individual tree. Every tree has a separate validation set, as samples are bootstrapped for each tree.

### Out-of-Bag Samples

![Out-of-Bag Samples](https://i.ibb.co/KGPVLMg/Out-of-Bag-Samples.jpg)

The model is evaluated by checking the accuracy of every base tree on their respective out-of-bag samples. In other words, the OOB score is the mean prediction accuracy on each training point Xi using only the trees that do not have Xi in their bootstrapped sample that is used for building the model. Let’s understand this better.

Suppose there are N = **100** observations with M = **10** features and an outcome variable Y, which is categorical in nature. Now, you build a random forest model with **50 trees**. Then, calculate the OOB score as explained here.

For each observation Ni, Ni is passed to all the trees that did not have it in their training set. These trees then predict the class of Ni. The final prediction for Ni is decided by a majority vote. 

-   Point N1: Absent from the training set of 1o trees
    -   Actual value: 1
    -   Predicted output as '1' from 6 trees (correct)
    -   Predicted output as '0' from 4 trees
    -   Majority value: 1
-   Point N2: Absent from the training set of 15 trees
    -   Actual value: 0
    -   Predicted output as '1' from 10 trees
    -   Predicted output as '0' from 5 trees (correct)
    -   Majority value: 1
-   Point N3: Absent from the training set of 8 trees
    -   Actual value: 0
    -   Predicted output as '1' from 5 trees
    -   Predicted output as '0' from 3 trees (correct)
    -   Majority value: 1
-   For 2 points, the model has predicted correctly and incorrectly for one.
-   Hypothetically, if there are only three data points present in the data set, the OOB Score is 1/3.

If there are 100 observations, this is done for each observation in the training set. Once the predictions for every observation have been obtained using the majority votes, the OOB score is calculated as the count of the correct predictions as a proportion of the total number of data points in the data set. This can be represented as follows:

$$\text{Out of bag score}=\dfrac{\text{Number of correctly predicted values (out of bag)}}{\text{Total data points}}$$

The OOB error can be calculated as the count of incorrect predictions as a proportion of the total number of predictions on out-of-bag samples. This can be represented as follows:

$$\text{Out of bag error}=\dfrac{\text{Number of incorrectly predicted values (out of bag)}}{\text{Total data points}}$$

In the image given below, you can observe how a single observation is passed into the trees in which the observation is absent, and then, the output is predicted.

![Observation passed into trees where observation is absent](https://i.ibb.co/162Q8LD/Observation-passed-into-trees-where-observation-is-absent.png)

Though the OOB error is on unseen data, there is a disadvantage, as you use all the training data sets to calculate the OOB error. In other words, if the test data set differs from the unseen training data set, the model may not perform well. Hence, when the data set is large, one should definitely perform cross-validation (better to perform k-fold cross-validation). In the next video, let's try to understand this.

**VIDEO**

Now that you are clear as to how the model is to be evaluated, let's wrap up this segment by exploring the factors that could affect the performance of a random forest model. These are as follows:

-   **Correlation between trees in the forest:** As the model is based on ensembles, one of the main requirements of the model is diversity. If the base models are correlated, it means the ensemble lacks diversity and, hence, cannot perform better than the individual models.
-   **Weightage of base models in the final prediction based on performance (Stacking):** The performance of the final model can be enhanced further by running the base models through another classifier/regressor (similar to Stacking). It will help to put a weight on each base model for final prediction based on their performance. A stronger base model will have a higher weightage than a weaker base model. However, this can cause the problem of feature dominance and, hence, should be used with a check because it can lead to overfitting.

Now that you have a good understanding of out-of-bag error, try answering the following questions.

#### OOB Error

Qn: Which of the following data sets is used to calculate the OOB error?

- Training set

- Testing set

- Validation set

Ans: A. *Only the training set is used while calculating the OOB error, which is why it gives a good idea of model performance on the unseen data without using a test set.*

Qn: Which of the following statements is true?

- All the observations of the training set are used to calculate the OOB error.

- Only a subset of the observations of the training set is used to calculate the OOB error.

Ans: A. *Recall that all the observations of the training set are used to calculate the OOB error.*

Qn: Which of the following statements are correct with respect to the OOB Error?

- It is calculated using all the data points in the training data set as all points are available in the OOB for some tree or the other.

- OOB Error is beneficial in choosing the best tree when the data set is small.

- OOB Error is beneficial in choosing the best tree when the data set is huge.

- It should not be used as it does not show performance on unseen data.

Ans: A & B.

In the next segment, you will learn about the advantages, disadvantages and applications of the random forest model.
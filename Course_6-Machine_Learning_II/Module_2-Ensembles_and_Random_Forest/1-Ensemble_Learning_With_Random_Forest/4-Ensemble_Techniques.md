# Ensemble Techniques

In the previous segments, you were introduced to the concepts of ensemble models and compared how ensemble models perform against single models.

Now, it is also essential to learn how multiple models come together to solve the problems with a single model. In the forthcoming video, you will learn about this.

**VIDEO**

So, as Anjali mentioned, you expect a good model to have a **low bias** (average displacement of prediction from the actual point) and a **low variance** (spread of prediction compared with the actual point). However, in the case of ML models, it is difficult to find a balance between bias and variance, since there is a trade-off between the two. In other words, ‘on one hand, the models should not be so simple as to not identify even the important patterns present in the data; on the other hand, they should not be so complex to even learn the noise present in the data set’.

  
You can arrive at this solution through either a single model or an ensemble. By combining several weak learners, **ensemble learning methods create a strong learner, thus reducing the bias and/or variance of the individual models**.

A model that works extremely well on the training set (low bias) may not be generalisable (high variance), thus resulting in an overfitted model. On the other hand, if a model is highly generalised (low variance), then it does not capture the underlying data (high bias), thus resulting in an underfitted model. 

## Bias–Variance Trade-Off

![Bias-Variance Trade-Off](https://i.ibb.co/7CftMSK/Bias-Variance-Trade-Off.png)

So far, you have learnt about three different algorithms (linear regression, logistic regression and decision trees). Among them, the decision tree experiences the problem of high variance and others to a little extent, depending upon the data set. This happens as you try to obtain the most accurate results over the training set, which leads to overfitting.

### Ensemble Models

Qn: Which of the following statements with respect to base models in ensemble learning is/are true?

1. They suffer from high variance, so they overfit on the training data.  
2. They suffer from high bias, so they are not able to understand complex problems.  
3. They are robust models, so they do not overfit/underfit on the training data.

- 1 and 2 only

- 2 and 3 only

- 1 and 3 only

- None of them

Ans: A. *As you have learnt, by combining several weak learners, **ensemble learning methods create a strong learner, reducing the bias and/or variance of the individual models**.*

#### Overfitting

Qn: Why does a decision tree model overfit in comparison with linear and logistic regression?

- Linear and logistic regression are based on the assumption of linearity between the dependent and independent variables.

- When built deep, decision trees can generate one leaf for each data point, and this leads to overfitting.

- The mentioned case is incorrect. The decision trees never overfit.

Ans: B. *With the increase in depth, decision trees try to follow the training set rather than generalising the model. Hence, it results in overfitting.*

In this segment, you will learn about some popular approaches to ensemble techniques:

-   Voting
-   Stacking
-   Blending
-   Boosting
-   Bagging

Random forests are built with the help of bagging as the ensemble technique, with some additional improvements, and are extremely powerful at reducing the variance of an algorithm. 

In the next video, we will start with the concepts of voting, stacking and blending.

**VIDEO**

### Voting/Averaging

In **voting/averaging**, different algorithms are combined to create an ensemble model by taking a vote or an average. Here, each model has an equal say in the final output. They are two of the easiest ensemble methods, which are quite easy to implement. For classification, we use voting, and for regression, we use the average of all the predictions made by the individual models.

![Voting Averaging](https://i.ibb.co/tK1HVcT/Voting-Averaging.jpg)

### Stacking

In voting, you saw that each model has an equal say in the final output. However, the weights allocated to the different base models can be varied to generate the final results.

A base model that performs better than other models can be assigned a higher weightage in decision-making. This is the high-level approach followed in **stacking** and **blending**. The outputs of the base models are passed through a level-2 classifier or regressor. This classifier assigns a weight over the output of every base model. In this way, the individual models are combined with different weights to get the final prediction.

You can get an intuition of stacking in the image given below.

![Stacking](https://i.ibb.co/ZBSDgn8/Stacking.jpg)

### Averaging

Qn: Which of the following statements is true about averaging?

- It can be used in a regression problem only.

- It can be used in a classification problem only.

- It can be used for both regression and classification.

Ans: C. *The averaging technique can be used in both cases. In a regression problem, you can directly average the prediction from different models. For a classification problem, you can apply this technique if the base models result in the probability of each class.*

#### Multiclass Logistic Regression

Qn: Can multiclass logistic regression be considered an ensemble model? (You can visit the segment on Multiclass Logistic Regression in the Logistic Regression module before answering this question.)

- Yes

- No

Ans: A. *The outputs from multiple logistic regression models are built for each class in a multiclass logistic regression model. These outputs serve as inputs to the softmax function, which assigns weights internally to the different models. Here, softmax acts as a level-2 classifier.*

## Bagging

In the forthcoming video, you will learn about another popular ensemble technique: bagging.

**VIDEO**

Bagging exploits the feature of ‘diversity’ in ensembles. A sample data set is used to generate different training subsets (with replacement), and an algorithm with the same set of hyperparameters is built on every subset of the sample data. In this way, different parts of the data set are exposed to the same algorithm, resulting in a variation among the individual models. Finally, the predictions from the individual models are combined by taking an average of all the values for a regression problem or a majority vote for a classification problem.

Bagging works well with algorithms that are unstable and result in a high variation with a few changes to the data – in other words, models that have a high variance. If you recall, decision trees tend to suffer from this problem if the hyperparameters are not tuned properly. Hence, bagging works extremely well for high-variance models such as decision trees. Random forests are built on this approach, with some additional improvements, and are extremely powerful at reducing the variance of an algorithm. 

However, bagging has certain disadvantages as well. With this approach, you cannot explore or justify the individual models, as the data is selected randomly for each subset. Hence, you do not know the basis for the base models and rely on the final results provided by the combined model. This leads to a loss of interpretability. Moreover, since multiple models are built simultaneously, bagging can be computationally expensive and is applied on a case-to-case basis. Another disadvantage that Rahim mentioned in the video is that a single feature may be so important that it is the only one that gets used in all the trees; this reduces the diversity of the ensemble method of bagging.

#### Bagging

Qn: How do we tackle the situation when a single feature, say, ‘A’, is used to split in all the trees in bagging?

- Use a random set of features for splitting in every tree of the ensemble

- Remove the feature from the model

- Use a random set of features at every split in every tree of the ensemble

- Cannot be tackled

Ans: A & C. *This will ensure that ‘A’ is not used in every tree, and even better, not at every split.*

In the next segment, you will learn about another popular ensemble algorithm: boosting.
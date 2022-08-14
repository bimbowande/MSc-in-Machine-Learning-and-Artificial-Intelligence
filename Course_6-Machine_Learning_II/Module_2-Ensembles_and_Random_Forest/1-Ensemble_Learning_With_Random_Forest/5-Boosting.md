# Boosting

In the previous segment, you learnt about bagging and some other ensemble techniques. Now, in this segment, you will learn about another important technique: boosting.

**VIDEO**

**Boosting**, as you learnt, is one of the most popular ensemble techniques. It can be used with any algorithm, as it generates weak learners sequentially to create an ensemble of weak learners, which, in turn, has an excellent performance.

The image below summarises the working of adaptive boosting. The first model towards the extreme left has misclassified the positive points, which are labelled below. Hence, the next model that is built focusses on classifying these misclassified data points in order to build the models, and so, the result is that the second model is in the middle. The second model has misclassified the three negative data points shown below; thus, the third model that is built focusses on classifying these data points correctly. When you combine the three models, you get the model given below, which classifies the data points perfectly. This is the algorithm followed by one of the boosting methods: Adaptive boosting. Another commonly used boosting method is that of [gradient boosting](https://explained.ai/gradient-boosting/L2-loss.html#sec:2.3).

### Adaptive Boosting

![Adaptive Boosting](https://i.ibb.co/DkysK1J/Adaptive-Boosting.png)

In the next video, you will get an overview of bagging and boosting, and we will compare the two.

**VIDEO**

We differentiate the different types of ensemble learning models based on how we connect the individual models.

### Bagging

![Bagging](https://i.ibb.co/47vZgw4/Bagging.jpg)

In bagging, models that are **parallelly connected** learn independently from each other. The output is then combined using some type of deterministic averaging process in order to create a strong learner by the end. As you learnt, the random forest, which is one of the bagging models, is composed of deep decision trees to create a forest that has a **low variance**. This ensemble model, therefore, **resolves the problem of overfitting**, which you encounter when you work with individual decision trees. 

### Boosting

![Boosting](https://i.ibb.co/ZzS5Fd4/Boosting.jpg)

On the other hand, in boosting, weak models are **connected sequentially** in such a way that the subsequent models are dependent upon the errors of the previous model. This type of model is preferred to connect weak learners with a high bias and a low variance because boosting **reduces the overall bias of the resulting strong model**. 

All the techniques mentioned above are capable of solving classification and regression problems, as it is an ensemble of decision trees. The working is almost similar, except for the aggregation of models. An average of the predictions is taken in the case of regression, unlike majority voting in classification ensembles. For more information on these methods, you can go through the SkLearn documentation [here](https://scikit-learn.org/stable/modules/ensemble.html).

#### Bagging

Qn: What do you understand by bootstrap aggregation?

Ans: *Bootstrap aggregation involves the following two things:*

1. _**Bootstrapping:** Sampling with replacement_

2. _**Aggregation:** Aggregating the models built on the bootstrapped samples_

*A key point to note here is the technique of sampling with replacement. This ensures that a particular sample can have the same data point repeated. This ensures that the samples are truly random and different from each other. If sampled without replacement, every data point sampled depends upon the existing distribution.*

#### Bagging vs Boosting

Qn: Which of the following methods uses weak learners to create an ensemble?

- Bagging 

- Boosting

Ans: B.

Qn: Which of the following statements about bagging and boosting is/are true?

- The aim of bagging is to reduce bias and not variance.

- The aim of bagging is to reduce variance and not bias.

- The aim of boosting is to reduce bias and not variance.

- The aim of boosting is to reduce variance and not bias.

Ans: B & C. _Bagging is suitable for high-variance, low-bias models, i.e., complex models, such as decision trees. Hence, it is efficient in **reducing overfitting**. Boosting is suitable for high-bias, low-variance models, i.e., simple models, such as linear regression. Hence, it is efficient in **increasing complexity and preventing underfitting**._

In the next segment, you will start with the random forest algorithm.

## Additional Reading

You can visit the link provided to gain a deeper understanding of regression using [ensembles](https://www.mlsurveys.com/papers/80.pdf).
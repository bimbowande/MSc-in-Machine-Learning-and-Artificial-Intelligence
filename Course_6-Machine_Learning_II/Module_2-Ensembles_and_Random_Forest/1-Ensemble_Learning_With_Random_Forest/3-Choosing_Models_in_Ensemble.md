# Choosing Models in Ensemble

So far, you learnt how ensemble learning can yield better results than a single model. However, this can only happen when you combine the correct set of models to obtain the final result. This segment will help you understand this.

In the video given below, you will learn how to select the models for ensemble learning.

**VIDEO**

You learnt that the two main criteria to choose a model for ensemble learning are diversity and acceptability.

Ensembles of models are somewhat analogous to teams of individual players. If you were to choose a football team, you would choose the players as follows:

- Players with different skill sets, such as defenders, attackers and a goalkeeper, to ensure **diversity**
- Good players, i.e., all players are **acceptable** based on their skill sets (and at least better than a regular person)

**Diversity** ensures that the models serve complementary purposes, which means that individual models make predictions independent of each other, and one model fills the gaps of others.

Ensembles are more robust with respect to the choice of the training data, which makes them more stable and less prone to overfitting. You will learn how the learning algorithm is designed to achieve independence and how it is beneficial.

**Acceptability** implies that each model is at least better than a random model. This is a lenient criterion for each model to be accepted into the ensemble, i.e., it has to be at least better than a random guesser.

#### Diversity and Acceptability

Given the model predictions for the data points shown below.

| Model  | Point 1 | Point 2 | Point 3 | Point 4 |
| ------ | ------- | ------- | ------- | ------- |
| Actual | 1       | 0       | 1       | 1       |
| M1     | 1       | 0       | 1       | 0       |

If you have to select the models to create the ensemble, which of the following models will you consider to include in the ensemble?

| Model | Point 1 | Point 2 | Point 3 | Point 4 |
| ----- | ------- | ------- | ------- | ------- |
| M2    | 1       | 0       | 0       | 1       |
| M3    | 0       | 0       | 1       | 0       |
| M4    | 1       | 0       | 1       | 0       |

- M2

- M3

- M4

Ans: A. *It has a good prediction rate and it is able to fill in the gaps of M1 by correctly predicting for Point 4.*

#### Credit Card Fraud Detection

Qn: You have seen in the previous module on Decision Trees that the Credit Card Fraud Detection Datasets are usually highly imbalanced. A typical data set would have 99% 0s and 1% 1s, where 0 stands for 'not fraud' and 1 stands for 'fraud'. Which of the following models can be included as a part of an ensemble if you consider accuracy as the criteria to choose upon?

- A model with 98% accuracy

- A model with 99.5% accuracy

Ans: B. *You can get 99% accuracy by labelling every data point as 0. Hence, any model that you use in the ensemble should have a better accuracy than this. This follows from the acceptability criteria.*

In the video, Pramod mentioned that the model is acceptable if the accuracy is greater than 50%. This is the case when the data set has an equal number of 1s and 0s. In case of fraud detection data sets, as you saw in the quiz given above, the acceptability criteria may keep changing.

Now, let’s watch the following video in which Rahim explain the different ways in which you can bring in diversity.

**VIDEO**

There are several ways in which you can bring diversity among the base models that you plan to include in your ensemble:

- Using different subsets of training data
- Using different training hyperparameters
- Using different classes of models
- Using different feature sets for each of the models

#### Diversity

Qn: What happens if the models in your ensemble are not diverse enough?

- Since the models are not diverse, they might give somewhat similar results; thus, the ensemble performance might not be much better than the individual models.

- Since the models are not diverse, they might give very different results; thus, the ensemble performance might not be much better than the individual models.

- Since the models are not diverse, they might give very different results; thus, the ensemble performance will be much better than the individual models.

- Since the models are not diverse, they might give somewhat similar results; thus, the ensemble performance will be much better than the individual models.

Ans: A. *More the diversity, more diverse will be the results in the ensemble; therefore, the ensemble will be equipped to handle and make predictions for a more diverse range of attributes. If the diversity is reduced, the models will give similar results, and hence, the ensemble performance might not be much better than the individual models.*

You can also use a combination of the ways given above in your models. In this segment, you learnt about the different ways to bring in diversity. Another criterion that is extremely important in ensembles is acceptability. Let’s understand this in more detail in the next segment.
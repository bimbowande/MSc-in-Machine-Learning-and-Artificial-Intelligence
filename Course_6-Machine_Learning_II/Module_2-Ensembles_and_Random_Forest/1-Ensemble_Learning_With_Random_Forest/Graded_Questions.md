# Graded Questions

Based on your learnings from this session, try to solve the graded questions given below.

All the best!

#### Ensembles

Qn: Which of the following statements is true?

- A larger number of trees would result in a lower variance of the ensemble.

- A larger number of trees would result in a higher variance of the ensemble.

- A larger number of trees would result in a lower generalisability of the ensemble.

Ans: A. *Variance refers to how much a model (here, an ensemble) changes with changes in the training data. If a large number of trees are at work, then even if some of them show high instability (extreme variation in the trees and their predictions), the ensemble as a whole would reduce the variance by averaging out the results of each tree.*

#### Ensemble Techniques

Qn: Which of the following statements about popular ensemble techniques is true?

- A random forest is identical to bagging since it is built on top of it.

- Boosting tries to combine independent models to build an ensemble model.

- Bagging is a sequential model, which tries to combine weak learners into strong learners.

- Stacking and blending when combined with bagging result in the random forest model.

- None of the above statements is true.

Ans: E. *This statement is true. Please find the justification for each option below:*

-    *Although the random forest algorithm is built on top of bagging, the algorithm has another set of optimisations, which are different from bagging. Hence, random forest is not identical to bagging.*

-   *The models in boosting are not independent of each other. The algorithm combines weak learners to generate a strong model.*

-   *The bagging algorithm is not based on the concept of weak learners. It is based on the concept of diversity in an ensemble.*

-   *Stacking and blending are not a part of the random forest algorithm.*

#### Bagging

Qn: The core idea behind bagging is to consider a majority score, rather than committing to a set of assumptions made by a single model. Which of the following is the reason why the core idea is particularly successful in random forests?

- Trees are inherently complex.

- Trees are typically unstable.

- Trees cannot overfit.

Ans: B. *If you have only one tree, then you have to rely on the decision that it makes. The decision made by a single tree (on unseen data) depends majorly upon the training data, since trees are unstable. On the other hand, in a forest, even if a few trees are unstable, averaging out their decisions ensures that you do not make mistakes because of the unstable behaviour of a few trees.*

#### Random Forests

Qn: Choose all the correct statements regarding a random forest.

- Bootstrapping implies that each tree in a random forest is built on randomly chosen observations.

- A random choice of features ensures that each tree is acceptable.

- While considering a split at a node, a random set of attributes is considered.

- The random choice of attributes while splitting at nodes ensures diversity in a random forest.

Ans: A, C & D. 

- *The word ‘random’ in random forests pertains to the random choice of bootstrapped observations.*

- *The random choice of attributes at each split of a tree ensures that prominent features do not appear in every tree, thus ensuring diversity.*

- *The random choice of attributes ensures that prominent features do not appear in every tree, thus ensuring diversity.*

#### Model Comparison

Qn: Which of the following is **NOT** a benefit of random forest over a decision tree?

- A random forest is more stable than a decision tree model.

- It reduces overfitting.

- Interpretability increases after using a random forest.

- It is immune to the curse of dimensionality.

Ans: C. *A random forest is like a black box model where you lose interpretability. A single decision tree would on any day be more interpretable than a random forest, which is a collection of trees.*

#### OOB Score

Suppose a random forest model is fit over a set of observations. Calculate the OOB score for the following scenario.

![OOB Score Qn](https://i.ibb.co/YPbkwnG/OOB-Score-Qn.jpg)

-   S.No. represents the observation number.
-   Y represents the actual value of the target variable (0/1).
-   Mk represents the base model trained over the bootstrapped sample.
-   ‘-’ denotes that the observation is present in the training set for the model.

- 1/6

- 1/3

- 2/3

- 5/6

Ans: C. *Four out of 6 observations are predicted correctly based on the majority score. Therefore, the OOB score is 4/6, which simplifies to **2/3**.*

# Introduction to Ensembles

The random forest algorithm combines multiple decision trees to generate the final results. This process of combining more than one model to make the final decision is termed as **Ensemble Learning**. So, before you learn about random forests, you must try to gain an understanding of ensembles.

An ensemble refers to a group of things viewed as a whole rather than individually. In an ensemble, a collection of models is used to make predictions, rather than individual models. Arguably, the most popular in the family of ensemble models is the random forest, which is an ensemble made by a combination of a large number of decision trees.

Let's hear more about it in this video.

Play Video

3221820

As mentioned in the video, sticking to a single model to build the final solution poses multiple disadvantages:

-   The model may be bound with a specific set of assumptions that the data may or may not follow. For example, if you fit a linear regression model, you imply that the target variable follows a linear relationship with the attributes. However, it is not always necessary and may lead to less accurate results.
-   Sticking to a single model also implies that the entire data set follows the same trend. If you can identify the variation in the relationship with the distribution of different attributes in the data, you can use multiple models to fine-tune the results. This is partly possible in decision trees, as the data is split based on different attributes; however, the model suffers from other challenges such as high variance and overfitting.

Ensembles try to overcome all these challenges by combining different models to predict the final results. These models are considered to be the base models, which are combined or aggregated using different techniques to produce the output. In principle, ensembles can be made by combining all types of models. An ensemble can have logistic regression and a few decision trees working in unison to solve a classification problem. 

![Ensemble Learning](https://i.ibb.co/0cZFfXZ/Ensemble-Learning.jpg)

## Ensemble Learning

Now, before you learn how ensembles work, the following questions may arise:

-   How does a collection of models work better than individual models?
-   How do you choose the individual models to form an ensemble such that it is better than any of the individual models?
-   How do you combine the individual models to get the best results?

#### Dictatorship vs Democracy

Qn: In the video, it has been mentioned that Democracy is better than Dictatorship in taking the correct decision. Can you think of how this can be translated to Random Forest?

Ans: *Both Dictatorship and Democracy involve decision-making by highly educated individuals. The only difference lies in the fact that, in a Democracy, decisions are made by a consensus of such individuals. More often than not, decision-making also takes more time. This is the case in Random Forest as you train multiple deep decision trees, and this increases the training time. The deep decision tree can be thought of highly educated individuals having different thoughts on a particular issue. You will be able to understand this better in future segments.*

#### Model Selection

Qn: Which of the following models can help you capture multiple trends in the data?

- Linear Regression

- Logistic Regression

- Decision trees

- Ensemble models

Ans: C & D. *A decision tree can capture multiple trends as it trains a separate model after each split. Ensemble model combines multiple models; hence, it inherently has the feature that captures many trends.*

You now have an understanding of ensembles. Results from multiple models combine to give a final result. However, various questions come to mind when you first hear about ensembles. In the following video, our expert will address them. 

**VIDEO**

As Pramod mentioned, all these questions will be answered one by one as part of this session. However, let's first understand the limitations faced in the approach with a single ML model.

-   It has been iterated multiple times that a single model will bound you with its assumptions; hence, the model may not be as generalisable as it should be.
-   Second, we deal with limited data to understand the relationship between variables and then finally replicate it over the unseen data. This means that the training data must be explored as extensively as possible to get a thorough understanding. This activity is restricted if you rely only on a single model. 

You are now aware of some of the shortcomings of using a single model. However, it is also essential to learn how multiple models come together to solve the problems present in a single model. In the next segment, you will understand why a collection of models can provide better results than those provided by a single model. You will also learn how to choose the base models for an ensemble.
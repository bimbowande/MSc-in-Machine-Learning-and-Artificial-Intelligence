# Summary

You have now reached the end of the first session of the module. In the forthcoming video, let's summarise your learnings from this session.

**VIDEO**

As part of this session, we covered the following topics:

-   **Introduction to ensemble learning:** The session introduced the concept of **ensembles** wherein multiple models combine to give you the final results. You also learnt about different ensemble techniques such as:
    -   Voting
    -   Stacking
    -   Blending
    -   Boosting
    -   Bagging

![Ensemble](https://i.ibb.co/FmJ0pPP/Ensemble.png)

-   **Benefits of ensemble methods:** Next, you learnt how ensemble learning helps overcome multiple challenges faced with an individual ML model. You learnt how base models could be combined to achieve a low bias and a low variance in the final model. 

![Error vs Model Complexity](https://i.ibb.co/q7bJTVB/Error-vs-Model-Complexity.jpg)

-   Next, you learnt about one of the most popular ?????ensemble models that use the bagging technique to combine the base models: **Random forest**.

![Random Forest Ensemble of Decision Trees](https://i.ibb.co/nQmkY5H/Random-Forest-Ensemble-of-Decision-Trees.jpg)

-   As part of this session, you learnt how random forests perform as compared with decision trees and other linear models in addition to their advantages and disadvantages. They combine multiple decision trees built on the same data set using different bootstrapped samples and different features for every split. It helps to reduce variance and allows further exploration of feature combinations.

![Random Forest Overview](https://i.ibb.co/zsy4kfZ/Random-Forest-Overview.png)

-   Finally, you learnt how to evaluate a random forest model with the help of the out-of-bag (OOB) score, which is mostly used when the data set is small. The higher the OOB score, the better the model is. The OOB score can be calculated as follows:  
      
    $$\text{Out of bag score}=\dfrac{\text{Number of correctly predicted values (out of bag)}}{\text{Total data points}}$$


    You also learnt that you should perform k-fold cross-validation to choose the best of the hyperparameters when you have a sufficiently large data set.
    

In the next sessions, you will learn how to build a random forest model using both Python and Spark.
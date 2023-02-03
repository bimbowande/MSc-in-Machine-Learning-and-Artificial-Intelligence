# SubTask: Stacking

In the previous segment, you learnt about the different models that need to be built as part of your training exercises. In this segment, we will discuss the third component of the modelling exercise, which involves building a stacking model. You may have come across Stacking as an ensemble technique while you were learning about Random Forest. In the next video, Arihant will quickly explain how Stacking works and how to use it while developing your model.

**VIDEO**

In the video above, you learnt about the Stacking technique. As you already know, Stacking is an [ensemble learning](https://courses.analyticsvidhya.com/courses/ensemble-learning-and-ensemble-learning-techniques?utm_source=blog&utm_medium=comprehensive-guide-for-ensemble-models) technique that uses predictions from multiple models (for example, decision trees, random forests or SVMs) to build a new model. This model is used for making predictions on the test data set.

The following steps are involved in using stacking for model building:  

-   First, you need to use K-fold cross-validation. Here, you train the base model on each fold and make predictions on their respective validation sets and collect those predictions. In this Capstone Project, your base models are the Logistic Regression and Random Forest models (Model Stack), as shown in the image given below.
    
-   Next, your predictions from the model stack (Logistic Regression and Random Forest) will be taken as features to the meta learner. In this case, the meta-learner is the XGBoost model, which will take in the probability predictions from the Logistic Regression and Random Forest models. Here, the target variable will be the same as the one you had used to train your Logistic Regression and Random Forest models. 
    
    ![Model Stacking](https://i.ibb.co/vsbVTWk/Model-Stacking.png)
    
-   After training the Meta-Learner, you need to use this meta-learner on the test data set to obtain the final predictions.
    

**Note**: In this Capstone Project, we have used one layer and one meta learner model to make the prediction. However, stacking models can also comprise multiple layers and meta learners.

In the next video, Arihant will explain the stacking architecture in detail.

**VIDEO**

In the video above, you learnt about the stacking architecture, which you will need to create to build your model. Let's go over the steps covered in the video.

1.  With the train data, you need to use the K-fold cross-validation. In the K-fold cross-validation, you need to split the entire data randomly into K folds (usually this value is between 5–10 depending on the data set). In the first iteration, the first fold is used to test the model, and the remaining K-1 folds are used to train the model.  In the second iteration, the second fold is used as the testing set, and the remaining folds are used as the training set. This process is repeated until each fold of the K folds has been used as the testing set. Finally, we take the average of the recorded scores, which will be the performance metric for the model.
2.  In order to use the K-fold cross-validation technique, you need to use the following base models:
    1.  Logistic Regression
    2.  Random Forest
3.  At the end of the K-fold cross-validation, the predictions need to be collected and shared with the meta learner (which, in this project, is XG Boost model). The XG Boost model will then be trained on top of these predictions.  
    **Note**: If the model is a **classification model**, then you need to feed in the **probabilistic predictions** to the meta learner. On the other hand, if it is a **regression model**, then you need to feed in the **regression outputs** to the meta learner. This is how stacking can be used as a Classification or Regression task.
4.  Finally, you need to use the meta learner, which, in our case, is the trained XG Boost model, on the test set to make the final predictions.

Now, you can create your stacking model on Python in the following ways:

-   **User-defined functions** (**UDFs)**, wherein you create your own ensemble models by yourself. However, since this is a time-consuming process, it is better to use available packages that have been provided below.
    
-   **mlxtend**
    
-   **vecstack**
    

We have chosen to teach you about the mlxtend package on Python, as it is a more than popular package than the others mentioned above. You can read about vecstack in this [link](https://towardsdatascience.com/automate-stacking-in-python-fc3e7834772e). Let's watch the next video to learn how to use the mlxtend package.

**VIDEO**

In the video above, you learnt how to use the mlxtend package on Python for implementing the stacking technique. The code used for the demonstration is provided below.

Download [Stacking-demo](model-stacking-explained--using-mlxtend.ipynb)

Download [train_sample](train_sample.csv)

Download [test_sample](test_sample.csv)

In the next segment, you will learn about the different evaluation metrics that you need to submit once your model is ready.
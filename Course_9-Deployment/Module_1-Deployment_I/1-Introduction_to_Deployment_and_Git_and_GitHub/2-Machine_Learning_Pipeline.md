# Machine Learning Pipeline

Machine learning pipeline describes the processes involved in productionizing a machine learning model, ranging from collecting data to evaluating the model.

In this segment, we will recap all the concepts that have already been covered in the module on **‘Machine Learning Pipeline’** of **Course 1** of this program, and you will understand how they are linked to this particular module.

Let's understand the machine learning pipeline in the next video.

**VIDEO**

So, let's summarize the video using an example. Suppose you want to predict whether a particular customer of a bank would avail a loan or not. The steps involved in this prediction are listed below:

1.  **Data acquisition:** The first step that you perform is to contact the bank and get the data set required for this prediction.
2.  **Data analysis:** After you have acquired the data through the bank or through surveys, the next step would be to analyse the data. You would identify various aspects of the data and the variables present in it.
3.  **Exploratory data analysis:** After you have analyzed the data, the next step is to draw meaningful insights from it. For that, you need to perform exploratory data analysis (EDA) and deal with issues like missing values and outliers, in addition to identifying categorical variables and performing univariate and bivariate analyses. You learned about EDA in the first module of this program, wherein Rahim performed the end-to-end EDA steps on bank marketing data.
4.  **Feature engineering:** After performing EDA, you will look for the different features that are present in the data and identify how many of them are the best fit for model training. In feature engineering step, you may use techniques like PCA (Principal Component Analysis), dimension reduction using p-values, techniques, etc.
5.  **Model training:** After you have performed all the steps of the machine learning pipeline, the next step is to identify the algorithm that gives us the best results.
6.  **Evaluation:** After training the model, it is evaluated on a different data set to analyze how well it has performed.

So, now that we have already built the model, the next step is to convert it into a product, and this is called the deployment of the model. This product can be used by someone who is not aware of machine learning. Anyone can derive benefits from a model once it has been deployed.

You can take the example of YouTube, which is being utilized by end users who do not have any knowledge whatsoever of machine learning but are eventually getting machine-learning-based recommendations using the deployed machine models in the back end.

#### ML Pipeline

Qn: What is the correct order of the machine learning pipeline?  
 
- Data analysis > EDA > Model training > Feature engineering 

- Data analysis > EDA > Feature engineering > Model training 

- Data acquisition > EDA > Data analysis > Feature engineering 

- Data analysis > EDA > Feature engineering > Evaluation

Ans: B. 

Before we go into the details of deployment, there are certain additional topics that are good to cover, namely **model packaging** and **retraining**.  Let’s learn about them in the next video.

**VIDEO**

Essentially, model retraining is necessary when there is a change in the data set with time. Model deployment is a continuous process, as it involves retraining a model whenever you find that the data has, over time, deviated significantly from the original training data. 

So, now that you know what model retraining is and how it impacts the quality of the results of the machine learning models, next, you will learn what **concept drift** is and how to find the best model. Let’s watch the next video to learn about this in more detail.

**VIDEO**

Consider an example where people are buying products from an online platform. The buying behavior of the customers may change with time. Now, suppose you have built a model that predicts sales based on input parameters such as money spent on marketing and promotions being run. The model is likely to become less and less accurate over time; this is a **concept drift**. In the merchandise sales application, one reason for a concept drift may be seasonality, which means shopping behavior changes seasonally. For example, the winter holiday season witnesses higher sales, whereas the summer holiday season witnesses lower sales. 

You can refer to the following website to learn more about concept drift:

[How Concept Drift Ruins Your Model Performance](https://towardsdatascience.com/concept-drift-can-ruin-your-model-performance-and-how-to-address-it-dff08f97e29b).

In the next segment, you will learn about the software architecture of the machine learning model deployment.

#### Concept Drift

Qn: Which of the following is a way to handle concept drift?

- Periodically updating the model with more recent historical data

- Using a weighting that is inversely proportional to the age of the data such that higher weight is given to the most recent data and less weight, to older data

- Designing systems to detect changes and choosing a specific and different model to make predictions

Ans: *All of the above.*

- *It is good to update the model with the new data so that the model accuracy increases.*

- *Older data may be less significant than new data in predicting with the use of an ML model. Thus, it is a good practice to assign weightage to data.*

- *There may be techniques to detect changes in data, based on which you can choose a specific and appropriate ML model to predict the results.*

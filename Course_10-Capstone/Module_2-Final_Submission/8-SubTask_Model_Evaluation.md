# SubTask: Model Evaluation

Now that your model is ready, let's learn about the various model evaluation metrics that you need to use to test the quality of your models and submit them as part of this Capstone Project. Let's watch the next video to go over these metrics.

**VIDEO**

In the video above, you learnt about the various evaluation metrics that you need to calculate after building the model. As discussed in the earlier segments, you will have to create separate models for gender prediction and age prediction.

**Gender Prediction**

This model is based on a binary classification model, wherein the final output is either male or female. Hence, you need to calculate and submit the following metrics after building this model:

-   Accuracy
    
-   Confusion Matrix (F1 Score, Precision, Recall)
    
-   ROC Curve and AUC
    
-   KS Statistic (Kolmogorov–Smirnov) 
    
-   Also, note down the probability bands identified through the KS table for the top three and bottom three deciles on the train data set.
    

You will have to submit these metrics for Scenario 1 and Scenario 2. Recall that since the information of some device ids may be missing, you will have to segregate the data into two sets, one with the complete information (Scenario 1) and the other with only partial information.

**Age Prediction**

As part of the age prediction exercise, you were given the option to create either a regression model or a classification model and provide proper reasoning for choosing between the two models.

1.  **Age Prediction Using Regression**  
    If you develop the regression model, you will have to submit the following evaluation metrics:
    -   **RMSE**
    -   **R-Squared**
    -   **Percentage population distribution** (on the train set and test set, which lies between +/- 25% of the actual and predicted value. Let the actual age be A and predicted age be P. The error between the actual age and the predicted age is given by the following formula:  
        (A−PA)×100  
          
         
2.  **Age Prediction Using Classification**  
    If you solve the age prediction problem as a classification problem, you will need to use the following evaluation metrics:
    -   **Accuracy**
        
    -   **Confusion Matrix (F1 Score, Precision, Recall)**  
        **Note**: Since the number of bins is three, your confusion matrix will also be a 3x3 matrix.
        
    -   **Multiclass Log-loss**  
        **Note**: You can refer to the sklearn documentation to implement this function.
        

You had learnt how to use the KS statistic for a logistic regression model during the credit card acceptance assignment. Let's hear from Arihant as he explains how the KS statistic is calculated for a classification model.

**VIDEO**

In the video above, you learnt how to calculate the KS statistic for a classification model. Let's revise the steps of calculating the KS statistic.

1.  Once the prediction probability scores are obtained, the observations are sorted by decreasing order of probability scores. This way, you can expect the rows at the top to be classified as 1s and the rows at the bottom to be classified as 0s.
    
2.  All observations are then split into equal-sized buckets (bins).
    
3.  Calculate the cumulative percentage of goods (1s / cumulative true positive rate) and the cumulative percentage of bads (0s /cumulative false-positive rate).
    
4.  At each bin, calculate the difference as the maximum difference between the cumulative percentage of goods and the cumulative percentage of bads.
    

The significance of the KS statistics is that it helps you understand what portion of the population should be targeted to obtain the highest response rate (1s). In the next segment, we will proceed to the next and final task for this Capstone Project: the Deployment of this model.
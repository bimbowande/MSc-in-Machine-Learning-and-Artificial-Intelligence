# SubTask: Designing Flask Application

In the previous segment, you got a brief overview of the various subtasks that you are required to complete as part of your deployment task. In this segment, we will discuss each of these subtasks in detail. In the next video, Arihant will explain the first subtask, which is '**designing the flask application**'.

**VIDEO**

You need to consider the following points while designing the flask application:

1.  As part of this subtask, you need to assume a random 50 Device_id from the test data set. **Note**: Each of these device ids should have the corresponding event information, as you need to consider only Scenario 1 for deployment (all information is present).
2.  As the second part of this subtask, you need to develop the following components of your flask application:
    -   Write the Main app.py, which includes the logic for making the predictions on the test data (this is already pre-processed).
    -   Load the saved test data that you had generated in the earlier stage.
    -   Load the respective pickle files (model.pkl) for your age and gender predictions.
    -   Present the corresponding age and gender predictions for the respective device ids in the form of a table. As you will be randomly choosing 50 device ids, it is expected that the final output will contain 50 age predictions and 50 gender predictions for the respective device ids.

Once you have created the flask application, it will be used for running various campaigns for driving different business KPIs. In the next video, Arihant will explain the **different campaigns** the company has in its portfolio and their respective target audiences.

**VIDEO**

As you learnt in the video above, gender and age prediction can help in increasing the revenue streams by targeting specific users for a specific campaign. These gender and age groups can be targeted through different channels such as SMS, push notifications and email.

For this Capstone Project, we have designed some specific campaigns targeting users based on their gender or age. Let's take a look at the several campaigns within them.

**Gender Prediction-Based Campaigns**

-   **Campaign 1**: Specific personalised fashion-related campaigns targeting female customers 
    
-   **Campaign 2**: Specific cashback offers on special days (International Women’s Day etc) targeting female customers
    
-   **Campaign 3:** Personalised call and data packs targeting male customers  

**Age Prediction-Based Campaigns**

-   **Campaign 4**: Bundled smartphone offers for the age group [0-24]
    
-   **Campaign 5**: Special offers for payment wallet offers [24-32]
    
-   **Campaign 6**: Special cashback offers for Privilege Membership [32+]  

Now that you have explored the different campaigns that we will be running, in the next video, you will learn how to map your customers with these specific campaigns (i.e., Campaign 1 to Campaign 6) in your flask application based on the prediction information.

**VIDEO**

So for, you have learnt that you need to create an app.py file (flask application), which will load the test data, and the model.pkl file, and output the 50 gender and age predictions in the form of a table. Now, let's take a look at the business logic that you need to incorporate into your flask application to map the device_id (in the test data) to these specific campaigns. 

-   **Gender prediction:** You will obtain your probabilistic gender predictions in the form of different deciles. Here, you need to utilise the bottom 3 deciles (8,9,10) and map them to class 0 and map the top 3 deciles(1,2,3) to class 1. Depending on your model, you need to check whether your class 0 is 'male' or 'female'. Using this logic, you can map your gender predictions to the device ids.
-   **Age prediction:** For the age prediction, you were given the option of using a regression model or a classification model.
    -   In the case of the **regression** model, you need to use the exact regression output and create buckets for your specific campaigns.
    -   Similarly, in the case of the **classification** model, you need to assign the customers to the class (age group) with the maximum probability.
-   After mapping your gender and age predictions to the respective device ids, you simply need to map these device ids to the given campaigns and present them in your output.

Finally, after your final flask application has been created, you need to dockerize this application and deploy it on your ec2 instance for further use.

Before you conclude the problem statement, let's watch the next video as Arihant will provide some more business context as to how the testing operations are conducted under similar business scenarios.  
  
_**Please note that the next video is not part of your Capstone implementation and has simply been provided as additional information.**_

**VIDEO**

In the video above, you learnt about the Champion Challenger model, which is a method that allows different approaches to testing operational decisions in production.

You have already learnt about A/B Testing in the earlier modules. In A/B testing, the goal is to conduct an experiment in which A and B are two variants, undertaken to determine which variant is the more effective, using hypothesis testing.

Now, let's come back to our challenger model scenario. Before deploying your models into production, you need to test the new or re-trained models (challenger model) on a small sample before making it accessible to the entire population. In simple terms, we allow the **original model (the champion)** and the **new or re-trained model (challenger model)** to compete against each other for a chance to become the new champion.

Let's assume that after creating the challenger model, we want to evaluate its performance under production. For this, we can make it available for 10% of the population and compare its performance against the performance of the champion model used by the remaining 90% population. If the challenger model works better than the champion model, then we know that the challenger model is holding good on the production sector, and slowly, we can increase the percentage population who have access to the challenger model.

![Champion Challenger](https://i.ibb.co/DL2KF2f/Champion-Challenger.png)

With this, we can conclude the problem statement and the different tasks expected to be completed as part of your Capstone Project. Good luck with your project!
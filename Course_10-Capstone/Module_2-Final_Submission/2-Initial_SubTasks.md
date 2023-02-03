# Initial SubTasks

Towards the end in Task 2, you had created three different data sets and dumped them in the s3 bucket. Now, as part of the next task of the model-building exercise, you need to read the data in the S3 bucket. In the next video, Arihant will explain the first three subtasks that you need to complete as part of the model-building exercise.

**VIDEO**

In the video above, Arihant provided a brief overview of the different subtasks that you need to complete as part of the model-building exercise. Let's take a look at each of these subtasks.

1.  **Reading data:** From your earlier tasks, your data which will now be present in the s3 bucket. You will have to create an ec2 instance to read and analyse the data for building your model.
    
2.  **Cleaning data**: Once you are able to read the data, you need to complete the appropriate data cleaning steps such as missing value treatment and imputation. An example of the data cleaning steps is the cleaning of the geospatial data. While exploring this data, you may come across zero values, which need to be taken care of.
    
3.  As part of the third subtask, you need to perform some basic **EDA and Visualisations**, followed by some **Feature Engineering,** which will help you build and improve your model.
    

Now, before we proceed to the next subtask, let's learn about the EDA and the feature engineering subtasks. In the next video, Arihant will walk you through the EDA tasks that you need to complete as part of this project.

**VIDEO**

In the video above, Arihant listed down all the EDA and Visualisations that you need to perform as part of this exercise. They are listed below for your reference.

1.  Plot appropriate graphs representing the distribution of age and gender in the data set [univariate].
    
2.  Boxplot analysis for gender and age [bivariate].
    
3.  Plot the percentage of the device_ids with and without event data. 
    
4.  Plot a graph representing the distribution of events over different days of a week. 
    
5.  Plot a graph representing the distribution of events per hour [for one-week data].
    
6.  The difference in the distribution of events per hour for Male and Female consumers. [Show the difference using an appropriate chart for one-week data.]
    
7.  Is there any difference in the distribution of Events for different Age Groups over different days of the week? [Consider the following age groups: 0–24, 25–32, 33–45, and 46+]
    
8.  Stacked bar chart for the top 10 mobile brands across male and female consumers.
    
9.  Prepare a chart representing the ten frequently used applications and their respective male and female percentage.
    
10.  List the top 10 mobile phone brands bought by customers by age groups. [Consider the following age groups: 0–24, 25–32, 33–45, and 46+]
    

In the next video, Arihant will share some feature engineering ideas that you can use while building your models.

**VIDEO**

In the video above, Arihant shared some ideas that can be used for feature engineering the data sets. Remember that you may or may not leverage these ideas, but in the end, you need to apply your understanding of the concept of feature engineering to generate the features that give the best results. Some of these ideas are as follows:

1.  Considering the events data, you can create a feature called Average Events, which can give you an estimate of how long the users' mobile phones are active.
2.  You can use the information related to the location of the users (latitude and longitude data) to create features representing changes in the latitude and longitude details at different times of the day.
3.  You can create features such as Median Latitude and Median Longitude for different event ids.
4.  You can also group the existing categories to create a new supercategory that will establish a significance in predicting the outcome variable.

In the next segment, Arihant will explain the next set of subtasks that you need to perform as part of the model-building exercise.
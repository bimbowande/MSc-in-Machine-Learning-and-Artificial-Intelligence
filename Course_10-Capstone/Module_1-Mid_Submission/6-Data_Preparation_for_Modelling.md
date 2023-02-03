# Data Preparation for Modelling

In the next video, Arihant will shed light on some data issues that will be present in your data set, which you need to account for while developing your model.

**VIDEO**

One of the Hive tasks is related to the event data. Now, the event data is captured when the user grants permission and their mobile phone is connected to the Internet. Considering user privacy, certain apps and mobile phones will not provide the event information. Therefore, your device data can be categorised into two sets of data. Let's consider the following two scenarios:

-   **Scenario 1**: The user allows the application to trigger events that collect their usage behaviour.
-   **Scenario 2**: User activity is unavailable, thereby leaving us with only the device information. Therefore, the event data will not be available.

Since the data and information present in both these scenarios are different, and neither of these scenarios can be ignored, you will have to tackle these scenarios separately during the model-building stage. We need to explore the complexities of this stage caused by the two scenarios when we reach Task 3 of the Capstone project.

## **Task 2: Data Preparation for Modelling**

In the next video, you will learn about the second task of your exercise, which involves preparing the data for modelling.

**VIDEO**

In the video above, you learnt how you need to prepare the data before proceeding to the modelling phase. You need to use the external Hive tables to categorise and create the data sets for your model-building activities. The tables, along with their primary keys for each table, are given below.

![Telecom Project Tables Primary Keys](https://i.ibb.co/wL2g8Jm/Telecom-Project-Tables-Primary-Keys.png)

Once you have completed this task, you are expected to report the shape of the different data sets and finally dump this data onto your S3.  You may find that the dataset representing Non-Event data is very huge so you may choose 

Note: Assume that the train data is your point of reference while creating event and non-event data by left join.

With this, you have reached the end of Capstone Part 1. In the next session, you will learn about the different subtasks involved in model building and deployment.
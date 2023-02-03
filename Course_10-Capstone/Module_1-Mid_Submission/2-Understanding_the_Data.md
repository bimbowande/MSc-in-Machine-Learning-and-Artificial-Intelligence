# Understanding the Data

In this segment, you develop an understanding of the different types of data that are available, followed by each column present in the data set. The data set can be divided into three major categories:

1.  User data with demographic information (train data)
2.  User-defining information 
3.  Metadata

Let's watch the next videos to learn about each of these categories in detail. But before you dive into each of these data sets, let's take a look at the entire relational database.

![Telecom Project Relational Database](https://i.ibb.co/QPWt0Q7/Telecom-Project-Relational-Database.png)

In the next video, Arihant will provide an overview of these data sets.

**VIDEO**

The information provided in this particular data set has been extracted from the SDK devices and collected from the customers with their consent. This type of data is known as alternate data because it comes from an alternate channel. In this case, the alternate channel is the SDK device. We will utilise this data to perform various customer analytics and predictive modelling. 

-   **train.csv**  
    This data set consists of the following columns:
    1.  **device_id**: The device_id column is the primary key of this data set and can uniquely identify each device in the data set. 
    2.  **gender**: This column takes in two values, 'male' and 'female'. As you learnt in the previous segment, you will be required to develop a binary classification model for predicting the gender for a device id present in the data set.
    3.  **age**: This feature depicts the age of the user. In addition to gender, age is one of the target variables that you will have to predict as part of this exercise.
    4.  **group**: This feature is essentially a combination of age buckets and gender. Please note that this is one of the outcome variables and cannot be used as a predictor variable while building models. 

In the next video, Arihant will focus on the user-defined information present in the following data sets:

-   brand_device
-   events
-   app_events

**VIDEO**

In the video above, Arihant explained the three data sets, **brand_device**, **events** and **app_events**. Let's take a look at the columns in each of these data sets.

-   **brand_device.csv**  
    This data set contains the device_id, device_model and the phone_brand columns. Both device_model and phone_brand columns are categorical variables.
    1.  **device_id**: The device_id column is the primary key of this data set.
    2.  **device_model**: This is the specific model of the mobile phone.
    3.  **phone_brand:** This is the brand of the mobile phone.

-   **events.csv**  
    This data set contains the following columns: 
    1.  **event_id**: The event id column is the primary key of this data set. Whenever the user tries to access any app, an event gets triggered and an event id is generated.
    2.  **device_id**: This is the id of the device. However, you may have multiple event ids for the same device id in this data set. This is because multiple events can be triggered by the same device.
    3.  **timestamp:** This is the timestamp when the event had occurred.
    4.  **longitude**: This is the longitudinal location of the user when the event was triggered.
    5.  **latitude**: This is the latitudinal location of the user when the event was triggered.

-   **app_events.csv**  
    This data set contains the event_id, app_id, is_installed and is_active columns. Note that the '**is_installed**' and '**is_active**'  columns are binary variables.
    1.  **event_id**: This is the identification for the event.
    2.  **app_id**: For any unique event id, the device will try to capture all the different app ids that are active at that particular moment. So, you may have multiple app ids for the same event id.
    3.  **is_installed****:** This column indicates whether or not the specific app id was **installed** when the event was triggered.
    4.  **is_active**: This column indicates whether or not the specific app id was **active** when the event was triggered.

In the next video, you will explore the **label_categories** and **app_labels** data sets.

**VIDEO**

In the video above, you explored the **label_categories** and **app_labels** data sets. Let's take a look at the columns in these data sets.

-   **app_labels .csv**  
    This data set contains the **app_id** and **label_id** columns. You may find a many-to-many relationship between them.
    1.  **app_id**: This is the unique id that belongs to the different apps present in the device.
    2.  **label_id**: This represents the category to which this app belongs, e.g., the app belonging to the finance and gaming categories will have different label ids. These labels will be present in the label_categories data set in the form of categories.

-   **label_categories****.csv**  
    This data set contains the app_id and label_id columns. Both device_model and phone_brand columns are categorical variables.
    1.  **label_id**: This is the unique id of the label.
    2.  **category**: This is the exact label of the app.

So, in a nutshell, the train data set mainly consists of the independent and target variables, and for creating the different independent variables, you have been provided with brand device details, events, app_events, label_categories and app_labels.

The brand device and train are mapped through the device_id column, which is the primary key in both the data sets. The events and app_events data sets are connected through the event_id column, which is the primary key. The app_event and app label data sets are connected through the app_id column, and finally, the app_labels and label_categories data sets are connected through label_id column.

Now that you have learnt about the different types of data available, in the next video, you will go through the structure of this database.

## **Sample Data Walkthrough**

Now that you have understood the entire structure of the database, let's watch the next video and take a look at some sample data of each data set.

**VIDEO**

You can the sample data set given below to understand the data that you will be using to build your models.

Download [Sample Data Walkthrough](Sample_Dataset.xlsx)

In the next segment, you will explore the architecture of the given data and learn about the different steps involved in the first activity of data ingestion and data analysis.
# SubTask: SQL and Hive Analysis

In this segment, Arihant will specify the different SQL and Hive tasks that you need to perform as part of this Capstone project. So, let's watch the next video for more details on this.

**VIDEO**

In the video above, Arihant explained the different SQL tasks that you need to perform as part of the sanity and count analysis. You need to perform these SQL tasks directly on top of the RDS instance using the SQL queries that you learnt about in the earlier modules. Let's take a look at the results that you need to submit in your report.

1.  Count of unique device ids in the train table 
    
2.  Check whether there are any duplicate device ids present in the brand_device table. If yes, how many duplicates?
    
3.  Number of unique phone brands from the brand_device table
    
4.  Count of device ids where the latitude and longitude detail are zero, from the events table

In the next video, Arihant will explain the different Hive tasks that you need to perform on the data set.

**VIDEO**

In the video above, you learnt about the different tasks you need to perform on Hive. Once you have the data on your EMR cluster, you need to create Hive tables and write HQL queries to get the following records:

1.  The 10 most popular brands and the percentage of the respective Male and Female owners of these brands [Handle the device id duplicates from brand_device  table.]
    
2.  The 10 most popular brands for Male and Female?  [Handle the device id duplicates from the brand_device data set.]
    
3.  The count and percentage analysis of the Gender in the train data set
    
4.  The top mobile phone brands offering the highest number of models [Provide details about the top three brands.]
    
5.  The average number of events per device id [Applicable to the device_id column from the train table, which has at least one associated event in the event table]
    
6.  Whether the count and percentage of the device_id column in the train table have corresponding events data available

In the next segment, you will learn about some data issues that you will need to tackle in this project going ahead. You will about learn about Task 2 of this exercise: Data Preparation for Modelling.
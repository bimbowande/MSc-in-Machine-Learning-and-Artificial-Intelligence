# Data Sources

In this segment, you will learn about the different sources from where your data will be extracted. You will also learn how to ingest this data for building your model. So, let's watch the next video to learn about the sources from where you need to extract your data set.

**VIDEO**

In the video above, you learnt about the different data sources from where you need to extract your data in order to build your model. The entire data is stored in the following two sources:

-   **AWS RDS**: The RDS information is given below.
    
```
    RDS Information:
    Endpoint/Hostname: mlc-testcapstone.cyaielc9bmnf.us-east-1.rds.amazonaws.com
    username: student
    password: STUDENT123
    db: mlctest
```
    
    You will have to use the following command to connect to this instance:
    
```
    Command to establish a connection to the instance
    mysql -h mlc-testcapstone.cyaielc9bmnf.us-east-1.rds.amazonaws.com -u student -p
    STUDENT123
    show databases;
```
    
    WIthin the RDS, you will find the following data sets:
    
    -   events
    -   app_events
    -   brand_devices
    -   train
-   **AWS S3**: You have been provided with the public s3 links for the following data sets:
    -   **app_labels**: [https://capstone-project-mlc-metadata.s3.amazonaws.com/app_labels_new.txt](https://capstone-project-mlc-metadata.s3.amazonaws.com/app_labels_new.txt)
    -   **label_categories**: [https://capstone-project-mlc-metadata.s3.amazonaws.com/label_categories.csv](https://capstone-project-mlc-metadata.s3.amazonaws.com/label_categories.csv)

## **Data Architecture**

Now that you have learnt about the various types of data involved in this project, it’s time to understand how to approach the task of building a solution to this problem statement. In the next video, you will understand how the entire architecture should look like.

Play Video

3221820

In the video above, you got an overview of the data ingestion workflow, from extracting the data from the respective data sources to generating them on the ec2 instance. Your data will be present in various data sources such as RDS and S3. The data ingestion process involves the following steps: 

-   Use the sqoop command to extract the data from RDS into your EMR. Similarly, you can use the S3 read command to get the s3 data on your EMR.
-   Once your data is accessible from the EMR, you need to create a different Hive table, wherein you will write different HQL queries and perform some high-level analysis. (You will learn about this in detail in the next segment.)
-   Next, you need to move this data to your personal s3 bucket. You can access the data later on your the Jupyter Notebook for building machine learning models.

![Telecom Project Data Architecture](https://i.ibb.co/s2ZWWsj/Telecom-Project-Data-Architecture.png)

In the next segment, you will learn about the ML life cycle and the high-level tasks, which you will be performing in the data ingestion and analysis phase.
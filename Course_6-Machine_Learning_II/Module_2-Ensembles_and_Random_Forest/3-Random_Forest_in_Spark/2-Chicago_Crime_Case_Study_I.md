# Chicago Crime Case Study - I

The Chicago crime case study is based on the crime record maintained by the Chicago Police Department. It is a detailed data set that stores the information associated with all the crimes that occur in the city (except murders for which data exists for each victim). The actual data set contains the records from the year 2001 until now. We will take part of this data set to build a simple recommendation model based on the random forest model. 

The data set involves multiple attributes associated with the crime, such as its location, type and description. Every crime also has an FBI code associated with it, which indicates the crime classification as outlined in the FBI's National Incident-Based Reporting System (NIBRS). This case study aims to recommend an FBI code based on the different attributes of the crime. This could help in the automatic filling of the FBI code in the police records whenever a new crime is reported.

In the next video, Sajan will introduce the problem statement and briefly talk about the data set available for building the model.

**VIDEO**

In this video, you saw that there are multiple attributes in the data set, which can be used to suggest the FBI code for the crime. You must go through the description of each variable to get a good understanding of the values stored in them. Let's start with loading the data set in the Spark environment and then try to understand it:

-   The data set can be accessed using the following public S3 link:  
    _s3a://chicago-crime-mlc/Chicago_Crimes_2012_to_2017.csv_
    
-   The file is named as _Chicago_Crimes_2012_to_2017.csv_.
    

This case study will require you to launch an EMR cluster with the following configuration:

-   Software configuration: **emr-5.30.1** (under advanced options)
    
-   1 master node and 2 slave nodes (**m4.large**)
    
-   Select the following services:
    
    -   Hadoop 2.8.5
        
    -   Livy 0.7.0
        
    -   Spark 2.4.5
        
-   Under the software settings, provide the following configuration:  
    _[{"classification":"livy-conf","properties":{"livy.server.session.timeout":"3h"}}]_
    

![AWS EMR Livy Config](https://i.ibb.co/KbzN2Sh/EMR-Livy-Config.jpg)

-   You will also be required to configure the Spark driver memory that has been provided in the Jupyter Notebook. You must run all the commands provided in the notebook before starting with the steps involved in the case study.
    

In the next video, you will learn more about the attributes of the data set.

**VIDEO**

In the video, Sajan explained each attribute in the data set and its importance in classification. The data set can be successfully loaded in the Spark environment using the S3 link of the file. There are approximately 14.5 lakh crime records, with information stored for 23 different variables.

Note that we do not infer the schema of the data set purposefully. It is done because most of the variables in the data set (such as 'IUCR' and 'Beat') are stored as integer values. However, they do not represent an ordered series. Every value represents a specific category of the variable. Therefore, we must treat them as categorical variables instead of continuous variables.

#### Data understanding

Qn: Which of the following attributes of the Chicago Crime Dataset primarily identifies the type of crime?

- Arrest

- IUCR

- Primary Type

- Location Description

Ans: C. *Primary Type identifies which crime type is committed, e.g., battery, theft and so on.*

By now, you are aware of the different features of the data set that can be used to obtain the FBI code for a crime. In the next segment, you will start with the implementation of the same in Spark.
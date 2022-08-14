# Introduction

Welcome to the session on 'Random Forest in Spark'.

In the previous session, you learnt how to build a random forest model using the sklearn library in Python. In this session, you will carry out the same exercise using PySpark. The two main objectives of this session are as follows:

-   Spark case study: Chicago crime
    
-   Optimisation of the random forest algorithm in Spark
    

Let’s hear more about the session by Sajan in the following video.

**VIDEO**

The objective of the Chicago crime case study is to recommend the correct FBI code for each crime. This case study will be performed on the Amazon EMR cluster. So far, you have worked only with binomial classification problems. The Chicago crime case study will give you exposure with respect to solving a multiclass classification problem in PySpark using Random Forest. Sajan will walk you through the problem statement in detail in the following segments.

After the process of model building, in the session, you will learn about the optimisation techniques that can be used to run the algorithm smoothly in Spark. 

As part of this session, you must keep the following in mind:

-   You need to launch a **three-node cluster** (one master and two slaves) with the instance type as **m4.large**.
    
-   You must terminate the cluster when not in use, as future modules will also require the support of EMR.
    
-   You must follow the steps mentioned in the videos and should only experiment once the required tasks are complete.
    
-   Since the data set is huge, it is advised that you use your learning from previous modules and optimise the process by storing the intermediate data frame in the form of parquet. This will help you save time and cluster cost, as you will not have to run the same steps again after termination.
    

You can download the notebook used in this session from the links given below.

Download [RF notebook]()

Now, let's proceed with the session.

## People you will hear from in this session

**Subject matter expert**

[Sajan Kedia](http://in.linkedin.com/in/sajan-kedia-b06a6821)

Data Science Lead - Myntra

Sajan has completed his undergraduate and postgraduate education in Computer Science Engineering from IIT, BHU. He heads the pricing team at Myntra, where he actively works on technologies such as data science, big data, Spark and machine learning. Presently, his work mainly involves the development of discounting strategies for all the products offered by Myntra.
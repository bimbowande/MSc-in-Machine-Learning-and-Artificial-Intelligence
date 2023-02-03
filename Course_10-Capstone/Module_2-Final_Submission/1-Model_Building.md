# Model Building

Welcome to the second part of the Capstone Project!

In the first part of the Capstone Project, you were expected to complete the data ingestion process and create the appropriate tables essential for our modelling activities. In this part of the Capstone Project, you are expected to build machine learning models and deploy them. In the upcoming segments, you will be briefed on the set of subtasks that you are expected to complete as part of the model-building and deployment phase.

**Important Note**

These subtasks will give you an idea about the approach that you may have to take while solving the problem statement. More research is expected from your end in solving and attempting each of these subtasks.

**Model Building Subtasks**

1.  Reading Data
    
    -   Read the data from S3 in EC2
        
2.  Cleaning Data
    
    -   Example: Geospatial Data (Lat and Long)
        
    -   Other Data Cleaning required
        
3.  Basic EDA and Visualisation and Feature Engineering Ideas
    
4.  Advanced Visualisation and Clustering
    
    -   Geospatial Visualisation
        
    -   DBSCAN Clustering as a preprocessing technique
        
    -   Final Data Preparation and Train-Test Splitting
        
5.  Model Building: Different Models
    
    -   Segmenting the data [Scenario 1 and Scenario 2] 
        
    -   Gender and Age Prediction
        
    -   Model Evaluation
        

**Deployment Subtasks**

1.  Select the best model based on the model evaluation metrics for only Scenario 1 [age and gender prediction]
    
2.  Export the models as pickle files and save the pickle files
    
3.  Keep the test split created prior to the model building phase safe in order to integrate it with the flask application
    
4.  Create a flask application that can be exposed as an API endpoint 
    
    -   Design a flask application
        
    -   Dockerize the application
        
    -   Deploy the application on EC2

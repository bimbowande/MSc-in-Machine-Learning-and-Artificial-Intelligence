# Module Summary

With this, you have completed the module on Deployment. The following topics were covered in this module:

### Introduction to Deployment and Git and GitHub

-   Machine Learning Pipeline: The machine learning pipeline can be summarized in the following steps:

1.  Data acquisition
2.  Data analysis
3.  Exploratory data analysis
4.  Feature engineering
5.  Model training
6.  Evaluation

-   Git and GitHub: Git is nothing but a version control system, and GitHub is a social code-hosting platform where you can look into open-source code and suggest changes in the code.   
    It also offers you the functionality of hosting websites directly from your repository.  
     
### APIs and Overview of Flask

-   API stands for Application Programming Interface. It is a set of protocols and tools that help build software. API is a software intermediary that allows two applications to interact with each other.
-   REST is an acronym for Representational State Transfer. REST is the set of rules that are followed while creating APIs to ease communication. A system is known as RESTFUL if it follows all the given constraints. As per these rules or constraints, we should be able to get data when we link to a certain URL. The data that we receive is called a resource, and the URL from which we want to get the data is called a request.
-   Flask: Whenever we develop a web application in Python, we need a framework that can help us build web applications such that can improve the whole deployment process. Flask is used to support the development of web applications. For deploying our model, we will choose Flask. Here are a couple of reasons why Flask is preferred:  
    - More Pythonic than Django web framework  
    - Easy to set up and simple to use  
    - Extensive documentation  
    - Unit testing support integrate  
    - Built-in development server and debugger  
     
### Deployment of an ML Model Using Flask and Heroku

In this session, you deployed an end-to-end ML application using Heroku and Flask.

You have performed the following steps to deploy the model:

Firstly, you encapsulated the ML model using Pickle. As a data scientist, you will use various types of data in the form of dictionaries, DataFrames, or any other data type. When working with these data types, you may want to save them to a file, so you can use them later or send them to someone else. This is what Python's pickle module is for. It serializes the objects (save to the disk), so they can be saved to a file and loaded in a program later on. Pickle is used for serializing and de-serializing Python objects.

So, as you saw when you ran the code, it creates a new file named model.pkl, which can be used for the Flask application to orchestrate it with the ML model.

Once you have encapsulated the model, the next task is to create a web page through which the users will interact with the application. You created an index.html file containing all the headers and inputs for the application.

Once you have created HTML code and a linear regression model, the next step is orchestration. One of the important concepts that you need to understand here is that the app.py file works as the orchestration between the index.html and model.pkl files.

Now from here, you can get the local link to the web application and can predict the price of the house after pasting the URL in the browser.

-   **What Is Heroku**

Heroku is a platform as a service (PaaS) that helps developers in building, running, and operating applications entirely in the cloud.   
 

### Docker and Its Applications

What Is Docker?   
Docker is like a big container that comes in one shape and size, and fits in a truck used for transporting goods from one place to another. The contents of the boxes do not matter as long as they are packed in containers so that you can transport the goods easily without worrying about the dimensions of the goods.

  
Docker is similar to that container. It does not matter on which system you have deployed the model; once the code is containerized on Docker, the model can be used across all the platforms and will not face issues of dependency.

  
When Docker was first introduced, it was compared to virtual machines owing to the similarity in terms of how the two function. Docker can be seen as something that uses less memory and starts faster than a virtual machine.

### Terminologies Related to Docker

**Docker:** Docker is a containerization platform that packages your application and all of its dependencies together in the form of a Docker container to ensure that your application works seamlessly in any environment.

**Container**: Docker Container is a standardized unit that can be created on the fly to deploy a particular application or environment. 

**Docker Image:** A Docker image is a read-only template that contains a set of instructions for creating a container that can run on the Docker platform. It provides a way to package applications and preconfigured server environments that can be used for personal purposes or shared publicly with other Docker users. 
  
Next, you deployed an ML model using Docker on your local machine. Further, you deployed an ML model on EC2 and created a public web application.

With this, you have successfully completed the module on Deployment using Flask, Heroku, Docker, and EC2.
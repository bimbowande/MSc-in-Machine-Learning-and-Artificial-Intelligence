# Summary

You have completed the session on ML model deployment using Flask and Heroku.

In the session, you went through a dedicated case study on house price prediction, in which you built a linear regression model and deployed it using Flask.

Also, you learned these steps to deploy the model:  
 

-   First, you encapsulated the ML model using “pickle.” As data scientists, you will be using different types of data in the form of dictionaries, DataFrames or in other data types When working with these data types, you may want to save them to a file so that you can use them later or send them to someone. This is what Python's pickle module is for.  
    It serializes objects (saves them to disk) so that they can be saved to a file and loaded in a program again later.

Pickle is used for serializing and deserializing Python objects.

When you run code, you will see that it creates a new file named model.pkl, which can be used by the Flask application to orchestrate it with the ML model.

-   Once you have encapsulated the model, the next task is to create a web page through which users will interact with the application. Then you have to create a file called “index.html," which contains all the headers and inputs for the application.

![Predict House Price](https://i.ibb.co/yNGX0Xc/Predict-House-Price.png)

Once you have created HTML code and a linear regression model, the next step is orchestration. One of the most important concepts that you need to understand here is that the file “app.py” works as the orchestration between the “index.html” and the “model.pkl” file.

From here, you can get the local link to the web application and predict the price of a house after pasting the URL in the browser.

Further, you learned about cloud computing, and we discussed these four types of cloud computing and the differences between them:

1.  On-premises
2.  IaaS
3.  PaaS
4.  SaaS

We took a real-world example to help you understand the concepts better. 

  
Consider that you buy a car, and you own it. This will be your on-premise service.

  
Now, consider that you have taken a car on lease. In this case, you can choose your car and drive it, but you do not own it. This is infrastructure as a service.

  
Imagine that you are traveling in a taxi. Here, you do not own the car, nor can you drive it, although you can use the platform. This is platform as a service.

The fourth type is software as a service. This can be compared to a bus. Here, you do not have to do much; in other words, you only have to go to the bus stop and take a bus.

  
You learned about each type by understanding their definitions.

  
This table shows the differences between the four types.

![Different Types Cloud Computing](https://i.ibb.co/WPMcQfp/Different-Types-Cloud-Computing.png)

In the table, the pink cells indicate the services managed by vendors, whereas cells the blue ones indicate the services managed by servers.

  
  
**What Is Heroku?**

Heroku is a platform as a service that helps developers to build, run, and operate applications entirely in the cloud. In the next segment, you learned how to deploy an ML model using Heroku: 

-   Next, you learnt how to make a web application public using Heroku. So, to deploy an ML model using Heroku, you should have the following two files ready.

1.  Procfile: It is also called procedure file.
2.  requirements.txt: It contains the version requirement of all the libraries and tools that are essential for model deployment.

You need to inform Heroku, which is a platform as a service, about the OS and the different versions of the various applications that are required to deploy a model. All of this information is present in the file “requirement.txt.” If you look at the file “requirement.txt,” you will notice that it contains these tools and libraries:  
 

Flask==1.1.1 gunicorn==19.9.0 itsdangerous==1.1.0 Jinja2==2.10.1 MarkupSafe==1.1.1 Werkzeug==0.15.5 numpy>=1.9.2 scipy>=0.15.1 scikit-learn>=0.18 matplotlib>=1.4.3 pandas>=0.19

All the aforementioned tools and libraries are relevant to deploy ML models, and their versions are mentioned in this file.

Another file is the “Procfile” or the procedure file. In this file, you specify that it is a web application and a running HTTP server, which is Gunicorn in this case. Gunicorn is a Python HTTP server.   
 

Next, you followed the process to deploy an ML model using Heroku to get the public URL, which you can share with anyone.
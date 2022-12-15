# Software Architecture of Deployment

In the last two segments, you learned about the machine learning pipeline. After performing some preparatory steps, you trained the model and evaluated it. 

Now, what is the next step? How do we extract real values from the model predictions?

We cannot use a Jupyter Notebook for this purpose. We cannot train the model every time we want to get predictions from it.
  
For this purpose, we need to **deploy the machine learning model**. Let’s watch the next video to learn how.  

**VIDEO**

Let’s try to understand how to query into a particular website to get results. Suppose you want to get some information from a website. This task will be carried out through the following steps:

1.  The user would request some information.
2.  The user’s request would go through a web framework.
3.  The framework would help the user interact with the machine learning model.
4.  The machine learning model would then make predictions and respond to the user.

A machine learning model, once deployed, goes through these steps. Upon predicting the results, it sends the predictions back to the user through the web framework.  
 

The image given below depicts these steps.

![Software Architecture of Deployment](https://i.ibb.co/41g1GHL/Software-Architecture-of-Deployment.png)

In the next segment, you will learn about version control systems.
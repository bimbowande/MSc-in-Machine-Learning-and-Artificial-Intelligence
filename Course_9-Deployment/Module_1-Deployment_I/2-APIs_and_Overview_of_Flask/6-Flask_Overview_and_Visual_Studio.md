# Flask Overview & Visual Studio

In the previous segments, you learned about APIs, the REST framework, and the steps in deploying an ML model. You were also introduced to the Flask web framework. 

In this segment, you will learn more about Flask. You will be introduced to Visual Studio, a tool used for performing hands-on deployment, in the coming segments.

Let’s hear from Mithun as he explains the various aspects of Flask in detail.

**VIDEO**

As you already know, Flask is a Python API that allows you to develop web applications. Take a look at the following image to understand the workings of a web application (in our case, Flask).

![Software Architecture of Deployment](https://i.ibb.co/41g1GHL/Software-Architecture-of-Deployment.png)

1.  **Request from a user:** The web application receives a request from a user to provide an output that is relevant to the user based on the ML model's prediction.
2.  **Request model to make predictions:** After the application receives the request from the user, it calls the ML model to make predictions.
3.  **Get predictions:** The ML model package provides predictions based on the user’s query. 
4.  **Response to the user:** Finally, the web application responds to the user based on the predictions made by the ML model.

You will get an end-to-end demonstration of ML model deployment, and for this, you will perform hands-on using Visual Studio. In the next video, you will be introduced to Visual Studio.

**VIDEO**

You can download Visual Studio from the link given below.

[Visual Studio Download](https://code.visualstudio.com/download)

You can also install and launch Visual Studio from Anaconda by simply clicking on the VS icon, as shown below.

![Anaconda Navigator](https://i.ibb.co/nfrDftW/Anaconda-Navigator.png)

In the next segment, you will develop a basic application for Flask using the code for “Hello Flask”.
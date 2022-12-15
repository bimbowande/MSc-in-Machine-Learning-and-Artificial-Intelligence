# Deployment Steps

In the previous segment, you learned about the different elements of the REST framework. In this segment, you will get an idea of its deployment steps.

To make your machine learning model available to end users, you must deploy it. To deploy a model, you must perform various steps. Let's hear more about these steps from Abhay in the next video.

**VIDEO**

Let's summarize what you learned in the video in the following manner:

-   **Packaging of the ML model:** Once an ML model is trained, it must be saved somewhere. There are many Python libraries that can perform the packaging of an ML model; one such library is '**pickle**'. You will learn more about this library in the coming segments. The packaging of a model is also known as the serialization of the model.
-   **Building the application skeleton:** Once the ML model is ready, the next step is to prepare an end-to-end application that can interact with users. Suppose you have built a model that predicts whether a particular customer is fraudulent or not for a credit card transaction. Then, there will be an application that takes user inputs and makes predictions according to the machine learning model that has been packaged in the application. To do this, various endpoints that are identified by the “paths” must be configured.
-   **Testing the application:** This step involves testing the application that you have built by passing some data points as inputs to check whether the application and the ML model are working correctly or not.

All these steps will become clearer as you proceed through the next segments, where you will create an application in Flask.

In the next video, Abhay will explain the next two processes in detail.

**VIDEO**

-   **Packaging the application:** Docker is a tool designed to make it easier to create, deploy, and run applications using containers. Containers allow a developer to package up an application with all the parts that it needs, such as libraries and other dependencies, and deploy it as one package. By doing this, the developer can be assured that the application will run on any other operating system, regardless of any customized settings that the machine might have that could differ from the machine used for writing and testing the code initially. You will learn about Docker in the coming sessions.
-   **Designing a user interface:** A user interface refers to the front end of an application through which users interact.

In the next segment, you will learn about Flask and its features.
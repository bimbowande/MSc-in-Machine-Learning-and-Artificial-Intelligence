# Summary

You have successfully completed this session, which works as a basis for the deployment of ML models because you learned about an important concept of Flask.

Let’s summarize all the segments one by one:

-   API: API stands for application programming interface. It is a set of protocols and tools that help build software. API is a software intermediary that allows two applications to talk to each other.  
    Suppose you are using an application on your mobile phone. The application connects to the internet and sends data to a server. The server then retrieves that data, interprets it, performs the necessary actions on it, and sends it back to your phone via the application. The application then presents you with the information that you wanted in a readable way. All of this happens via an API.
-   REST: REST is an acronym for **representational state transfer.** It is a set of rules that are followed while creating an API in order to ease communication.  
    A system is known as **RESTFUL** when it follows all the given constraints. As per these rules or constraints, you should be able to access data when you link to a certain URL. The data that you receive is called a **resource**, and the URL from which you want to access the data is called a **request**.  
    A URL consists of the following parts:

1.  Endpoint
2.  Methods
3.  Headers
4.  Data (Body)

-   **Endpoint:** This is the URL that you see in the address bar. 
-   **Path:** Suppose you have accessed a website, say, _http://github.com._ Now, suppose you want to get resources from a particular part of this website, and the URL for that is _http://github.com/tensorflow/tensorflow_ . Then, _tensorflow/tensorflow_ will be the path, and _http"//github.com_ will be the root endpoint.
-   **Method:** The resource methods used to perform a desired transition are one of the most important aspects associated with REST. Each URL has a set of methods associated with it, such as GET, POST, PUT, and DELETE. 
-   **Headers**: These are some of the elements that are passed along with the URL, such as an API token to verify a particular user. The HTTP headers are used to pass additional information between the clients and the server through the request and response header. 
-   **Data (Body)**: Details such as username and password used during login are passed as data in the URL. For instance, if you rate a movie on IMDb, the rating is passed as a data point in the body. 

 Two terms are associated with the REST API:

1.  **Client**: This is the application platform where you request resources. For example, when you use the Twitter API to search for tweets on the application, the application is your client.
2.  **Resource**: A resource is the information we send to any service. For example, when you interacted with the Twitter APIs, you received a set of tweets, which are resources.

The steps in performing deployment are as follows:

1.  **Packaging the ML model:** Once an ML model is trained, it must be saved somewhere. There are many Python libraries that can perform the packaging of an ML model; one such library is '**pickle**'. 
2.  **Building the application skeleton:** Once an ML model is ready, the next step is to prepare an end-to-end application that can interact with users. Suppose you have built a model that predicts whether a particular customer is fraudulent or not for a credit card. Then, there will be an application that takes user inputs and makes predictions according to the machine learning model that was built. In addition, you have been provided with a URL where you can interact with the application.  
3.  **Testing the application:** This step tests the application that you have built by putting some of the inputs to check whether or not the application and the ML model are working correctly.
4.  **Packaging the application:** Docker is a tool designed to make it easier to create, deploy, and run applications using containers. Containers allow a developer to package up an application with all the parts that it needs, such as libraries and other dependencies, and deploy it as one package. By doing this, the developer can be assured that the application will run on any other Linux machine, regardless of any customized settings that the machine might have, which can differ from the machine used for writing and testing the code initially.
5.  **Designing a user interface:** The design of a user interface includes the front end or the face of a website through which users interact.

-   Flask: Whenever you develop any web application in Python, you need a framework.  It helps you build a web application that can improve the entire deployment process. It is used to support the development of a web application. We chose Flask to deploy our model.  
    Some of the reasons why Flask is preferred are as follows:

1.  More Pythonic than the Django web framework
2.  Easy to set up and simple to use
3.  Extensive documentation
4.  Unit testing support integrate
5.  Built-in development server and debugger

The HTTP API approaches are as follows:

-   Representational state transfer (REST)
-   Remote procedure call (RPC)  
    These approaches have the following in common:

1.  **Resources**: This can be interpreted as the HTML files that are located on the server and are being accessed by the clients. 
2.  **Verbs**: To access resources, you use various verbs such as:

- GET: It is used to request data from a specified resource.  
- POST: It is used to send data to a server to create/update a resource.  
- PUT: It is used to send data to a server to replace / fully update a resource.  
- DELETE: It is used to delete a specified resource.

After that, you also saw a demonstration of GET and POST HTTP requests.

In the next session, you will learn how to perform an end-to-end ML model deployment using Flask and also take a look at how to develop a public web application using Heroku.
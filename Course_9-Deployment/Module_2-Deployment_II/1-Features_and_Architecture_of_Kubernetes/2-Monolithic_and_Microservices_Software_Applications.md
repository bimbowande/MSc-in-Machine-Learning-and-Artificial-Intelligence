# Monolithic and Microservices Software Applications

Let’s start discussing Kubernetes. First, you need to have an understanding of the monolithic and microservices software application. 

Let’s consider the example of Zomato. There are multiple pillars on which the whole application works, and they are as follows:

-   Notification to the users for new schemes and restaurants
-   Payment feature to pay for the food
-   Mailing feature to mail order details, payment receipts etc.
-   Assignment of the delivery boy
-   Tracking the food on google maps

Suppose all of the above features are interdependent on and interconnected with each other, which means that all the above-mentioned features are on the same code space, and every feature calls to a single server. This type of software application is called a monolithic application, which is built as a single unit. In the next video, Abhay will explain this.

**VIDEO**

Monolithic applications have the following drawbacks:

-   Every feature on the same code space leads to a situation wherein a single developer or a developers’ team cannot understand the application entirely.
-   Scaling of monolithic applications is a challenging task.
-   They are implemented using a single development stack (i.e., JEE or .NET), which can limit the availability of the correct tool for the job.

On the other hand, there are microservices software applications. In monolithic applications, everything related to codes and features is in a single unit, whereas in microservices software applications, everything is broken down into a collection of smaller services (conveniently named microservices).

Let’s understand more about this in the next video.

**VIDEO**

As in the example of the Zomato food delivery application, each service has its own API, and the interaction between services is through a JSON file. You can learn more about JSON by referring to the additional links provided at the end of this segment.

  
Each microservice can be deployed independently of the rest of the application. For example, an online retailer could have one microservice for inventory management and another for controlling their shipping service.

The key point to remember is that before you can take advantage of Kubernetes, your applications need to have a microservice architecture.

Some of the benefits of using microservices are as follows:

-   Microservices are highly maintainable and testable, as each feature is independent of each other.
-   Each service is independently deployable using Docker and container.
-   These are organised around business capabilities.
-   Each service can be owned by a small team.

Let’s consider a case wherein you want to add a service in this application, for example, a grocery delivery section, or suppose you want to descale the application and want to remove the mailing service from the application. What is the best way to achieve this?

One of the extremely popular methods to upscale or downscale an application is using Docker. Suppose you dockerise each service and want to shut down the mailing service. Then, you can simply stop the related docker from the application. If you want to add some new service, then you can simply create a new docker file for that. 

Dockerization of each service in the application will enable each service to run as an independent application. 

In the next segment, you will learn about the Kubernetes service. It helps with the scaling of applications in case they require more servers to run on.  
 

You can refer to the below additional links to learn more about JSON.

Additional links:  
[JSON_link-I](https://www.json.org/json-en.html)

[JSON_link-II](https://stackoverflow.com/questions/383692/what-is-json-and-why-would-i-use-it)

#### Microservices

Qn: Which of the following are the features of microservices software applications? (Multiple options may be correct)

- Each feature can be dockerized but you can not turn off or on individual dockers.

- Microservices software applications are implemented using a single development stack, which limits the availability of the right tool for the job.

- Each feature can be dockerized and when you want to upscale the application then you can add and run the Docker application related to the new feature.

- Each service is independently deployable using Docker and container

Ans: C & D.

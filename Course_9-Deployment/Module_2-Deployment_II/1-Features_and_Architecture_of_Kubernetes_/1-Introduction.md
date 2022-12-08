# Introduction

In the Deployment-I module, you learnt about the following tools and methods to deploy an ML model as a web application on a local system and cloud.

-   Git and GitHub
-   Flask
-   Heroku
-   Docker and deployment of an ML model on AWS EC2

ML model deployment is an essential part of making your application publicly available so that anyone can access it. In the upcoming video, you will be introduced to ML deployment.

**VIDEO**

In the Deployment- I module, you also learnt about Dockers. In this module, you will learn how a particular application is created using multiple microservices. 

Suppose you are creating an e-commerce web application, and you want it to have the following features:

-   The review section of the products
-   Email notification to the users regarding their orders and payment status
-   Payment system
-   Delivery management and tracking
-   Products inside your cart

Each of these services in the online shopping web application is created as a microservice using Docker and containers. Each service runs as its own group of dockers and containers that are interacting with each other.

So, you need to have a tool that can manage all the containers that are responsible for running the entire web application. 

In the previous module, you learnt that Docker is better than a virtual machine, as it is faster and uses lesser resources. Hence, the Docker container is a better way to bundle the application. 

Now, those containers (that are running for an application) need to be managed, and it should ensure that there is no downtime for any of the containers. This means that if one container goes down, then a new container should be started corresponding to the older one.   
 

The Kubernetes is the solution to similar use cases.

**In this module:**

You will learn about the following concepts:

-   Kubernetes features and its architecture
-   Deployment of an end-to-end ML model on Kubernetes using Kops (on AWS)
-   What the Minikube is
-   Kubeflow and its features
-   Kubeflow implementation on cloud

**In this session:**

You will learn about the following concepts:

-   Monolithic software applications
-   Microservices software applications
-   Features of the Kubernetes
-   Kubernetes architecture  

## People you will hear from in this module

Subject Matter Expert:

**[Abhay Raj Singh](https://www.linkedin.com/in/abhay263/)  
Machine Learning Engineer, Quantiphi**

Abhay is working as a Machine Learning Engineer with Quantiphi. He graduated from VIT University. He is an analytical professional with 3+ years of in-depth experience in solving multiple business problems across the retail and technology domain for Fortune 500 companies. Abhay’s work mostly revolves around computer vision and MLOps. He has been teaching data science for the last 2 years across multiple platforms located in India and the US.
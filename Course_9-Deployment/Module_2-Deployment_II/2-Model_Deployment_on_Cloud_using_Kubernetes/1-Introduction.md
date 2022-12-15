# Introduction

In the previous session, you learnt about the features and architecture of Kubernetes. In the microservice software application, each service runs as its own group of dockers and containers that are interacting with one another.

You need a tool that can manage all the containers responsible for running the entire web application.

As you learnt in the previous module, Docker is more efficient than a virtual machine because it is faster and uses fewer resources. Therefore, the Docker container is a better option for bundling the microservices of an application.

These containers (that are running for an application) need to be managed, and it should be that there is no downtime for any of the containers. This means that if one container goes down, then a new container should replace the old container.

Kubernetes is one such solution that can manage all of the above-mentioned behaviours.

In this session, you will learn how to deploy an end-to-end ML model on Kubernetes. You will work with AWS using Kops (Kubernetes Operations) to deploy the ML model.  

## In this session

You will learn about the following concepts:

-   Difference between Amazon EKS and Kops.
-   End to end hands-on of iris model deployment using Kops on AWS, which includes the following concepts:

1.  Creating an EC2 instance
2.  Installation of Kops and kubectl
3.  Creating S3 bucket and private hosted zone
4.  Define and create the Kubernetes cluster
5.  Amazon ECR and Amazon ECS
6.  Installation of Git and Docker on EC2
7.  Deploy an ML model

## People you will hear from in this module

Subject Matter Expert:

**[Abhay Raj Singh](https://www.linkedin.com/in/abhay263/)  
Machine Learning Engineer, Quantiphi**

Abhay is working as a Machine Learning Engineer at Quantiphi. He graduated from VIT University. He is an analytical professional with more than three years of in-depth experience in solving multiple business problems across the retail and technology domains for Fortune 500 companies. Abhay’s work mostly revolves around computer vision and MLOps. He has been teaching Data Science for the last two years across multiple platforms in India and the US.
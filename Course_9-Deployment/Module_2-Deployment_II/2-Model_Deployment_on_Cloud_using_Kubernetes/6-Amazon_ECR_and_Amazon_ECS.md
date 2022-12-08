# Amazon ECR and Amazon ECS

In the previous segment, you learnt how to create a Kubernetes cluster. Now let’s try to understand what the Amazon ECR service actually is. ECR stands for Elastic Container Registry and is a fully-managed Docker container registry that makes it easy for developers to store, manage and deploy Docker container images.

Let’s hear from Abhay as he explains the AWS ECR service in detail.

**VIDEO**

Amazon ECR is integrated with Amazon ECS (Elastic Container Services). Amazon ECS is a full-container orchestration service that is highly scalable and fast. ECS helps developers easily run, stop and manage containers on a cluster.  

After creating containers to run an application you can use ECS to host the containers that are responsible to run an application.

You can launch and stop container-based applications with simple API calls using Amazon ECS.

So, ultimately, after creating a Docker image, you need to push this image into ECR so that the Kubernetes cluster can receive this from ECR.

In the next segment, you will learn how to install Git and Docker on the EC2 instance.

Below are some additional links provided to understand more about ECS.

  
**Additional links**

[ECS link](https://aws.amazon.com/ecs/)

[ECR link](https://docs.aws.amazon.com/AmazonECR/latest/userguide/Registries.html)

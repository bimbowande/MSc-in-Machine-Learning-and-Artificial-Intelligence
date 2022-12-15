# Summary

With this, you have reached the end of the session on Kubernetes deployment. Let’s summarise your learnings from the session below.

-   **Amazon EKS vs Kops:**

You have seen that there are majorly two ways to deploy Kubernetes clusters on AWS.

1.  **Amazon EKS (Elastic Kubernetes Service):** EKS is a managed Kubernetes service provided by AWS. Using EKS, you can run Kubernetes on AWS without installing, operating and maintaining the Kubernetes control plane. EKS is an easily available and highly secure Kubernetes service. 
    
    EKS is a relatively new service and, hence, is not well-documented on the internet. Also, setting up a cluster with EKS is a bit more complicated than doing the same with Kops.  
     
    
2.  **Kops (Kubernetes Operations):** Kops is an open-source project that can be used for setting up a Kubernetes cluster on cloud services such as AWS and GCP. Kops is older than EKS, and hence, many industries use Kops for business deployment. It is a CLI tool that is known as the kubectl way of creating the clusters.

-   In the next segment, you set up an EC2 instance and created an IAM role for the instance. You also installed Kops and kubectl on EC2.
-   Next, you created an S3 bucket. S3 bucket is used for managing all the clusters that you created in the previous segment. Kops needs storage to track all the configurations and all the information related to the state of the cluster.
-   Next, you created a private hosted zone. Amazon Route 53 provides an easily available and highly scalable DNS and domain name registration. A hosted zone acts as a container for records. These records contain information about how you want to route the traffic for a specific domain (for example, upgrad.com) and its subdomains (for example, abc.upgrad.com or xyz.upgrad.com).

The master node communicates with all the worker nodes. The master node also needs to communicate with the etcd server, which is a storage system and that stores all the configuration data and information about the state of the cluster. So, to enable such communications, AWS provides the Route 53 hosted zone.

-   Defining the Kubernetes cluster: you have defined a Kubernetes cluster definition using the following lines of code:

```shell
kops create cluster \
--state=${KOPS_STATE_STORE} \
--node-count=2 \
--master-size=t2.micro \
--node-size=t2.micro \
--zones=us-east-1b \
--name=${KOPS_CLUSTER_NAME} \
--dns private \
--master-count 1
```

Once the cluster is defined, you have created a Kubernetes cluster using the _**kops update cluster --yes**_ command.

-   **Amazon ECS and ECR:** 

ECR stands for Elastic Container Registry and is a fully-managed Docker container registry that makes it easy for developers to store, manage and deploy Docker container images. It hosts the container images in an easily available and highly scalable architecture and allows you to deploy containers for your applications.

Amazon ECR is integrated with Amazon ECS (Elastic Container Services). Amazon ECS is a full container orchestration service that is highly scalable and fast. ECS helps developers easily run, stop and manage containers on a cluster.

-   In the next segment, you installed Docker and Git on the EC2 instance. You also created a Docker image and added the image to the ECR repository. Finally, you built an ML model using kubectl CLI and obtained the URL to run the web application.

With this, you have completed the project using Kubernetes.
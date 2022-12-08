# Module Summary

You have completed the module on Kubernetes, Minikube and Kubeflow. You have gone through the following topics:

-   **Feature and architecture of Kubernetes:** 

You have learnt the following things in this session.

- Monolithic and Microservices Software Applications: Monolithic software application: If all features are interdependent and interconnected to each other, which means that all the services are on the same code space and every feature is calling to a single server. On the other hand in microservices software applications, everything is broken down into a collection of smaller services (conveniently named microservices).

- Some of the benefits of using microservices are below:

1.  Microservices are highly maintainable and testable.
2.  Each service is independently deployable using Docker and container
3.  Organized around business capabilities
4.  Each service can be owned by a small team

- Kubernetes provides you with the following features-

1.  Load balancing
2.  Storage orchestration
3.  Automated rollouts and rollbacks
4.  Automatic bin packing
5.  Self-healing

- Various levels under which Kubernetes works:

1.  **Cluster:** Kubernetes is a distributed system where there are masters nodes and worker nodes which collectively constitutes a cluster of nodes.
2.  **Master and worker nodes:** Master node is used to manage and coordinate various nodes of the cluster which run the containerised application. 
3.  **Pods**: Kubernetes pods are the group of containers that are deployed together on the same host or the same worker node.
4.  **Control plane:** This is the centre of the Kubernetes cluster, the control plane is something that manages and coordinates various nodes of the cluster which run the containerised application.

There are four major components of the **control plane:**

1.  **Kube- etcd:** It can be interpreted as a database which stores configuration data and information about the state of the cluster in key-value format.
2.  **Kube- Scheduler:** The main task of the scheduler is to schedule/assign pods to the available nodes.
3.  **API Server:** It acts as the gateway to the cluster. The API server is the front end of the control plane which handles internal and external requests. It is the main management point of the entire cluster.
4.  **Controller- Manager:** It notices when nodes go down and respond accordingly. It is important to maintain the correct number of pods for any running application.

  
There are four major components of the **worker plane:**

1.  **Pods:** Pods can be interpreted as the group of the containers which are used to run an application.
2.  **Kubelet:** It is used as a relay for the information to and from the control plane. It interacts with etcd to read and write configuration and information data about the state of the cluster.
3.  **Kube- proxy:** It constantly looks for new services and appropriately creates rules on each node to forward traffic to services and to the backend pods, respectively.
4.  **Kubectl:** It is a platform which is used to pass commands to the cluster. It provides the command-line interface to run commands for the Kubernetes cluster.

**Kubectl**: It is a platform which is used to pass commands to the cluster. It provides the command-line interface to run commands for the Kubernetes cluster.

-   **Model Deployment on Cloud using Kubernetes:**

You have seen that there are majorly two ways to deploy Kubernetes clusters on AWS.

- **Amazon EKS (Elastic Kubernetes Service):** EKS is a managed Kubernetes service provided by AWS. Using EKS, you can run the Kubernetes on AWS without installing, operating, and maintaining the Kubernetes control plane. 

- **Kops (Kubernetes Operations):** Kops is an open-source project to set up the Kubernetes cluster on any cloud like AWS or GCP. Kops is older than EKS and hence it is more mature than EKS and many industries are only using Kops for their business deployment. Kops is a CLI tool and it is known as the kubectl way of creating the clusters.

**- Amazon ECS and ECR:** 

AWS ECR stands for Elastic Container Registry which is a fully-managed Docker container registry that makes it easy for developers to store, manage, and deploy Docker container images. It hosts the container images in a highly available and scalable architecture and allows you to deploy containers for your applications. 

ECR service is integrated with Amazon ECS (Elastic Container services). The ECS is a full container orchestration service which is highly scalable and fast. ECS makes it easy to run, stop and manage containers on a cluster.

-   **Minikube and Kubeflow: Concepts and deployment on EC2**

- **Minikube**: Minikube is a single-node Kubernetes cluster that is deployed using a virtual machine on your local machine. It is used to learn Kubernetes. Actual production systems use Kubernetes clusters with more number of master nodes and the worker nodes to achieve high availability.

  
- **Kubeflow** is an ML platform, which is designed to use ML pipelines to orchestrate complicated workflows running on Kubernetes clusters.

You can divide the whole Kubeflow overview into three parts:

1.  **ML tools:** You have a Kubeflow UI interface (You will have hands-on using Kubeflow interface in the further segments) which provides various ML tools which are required for your workflow like PyTorch, TensorFlow and XGBoost etc.
2.  **Kubeflow applications:** There are various applications that Kubefloe provides at its UI interface.
3.  **Platform/clouds:** There are various clouds services where you can deploy your Kubeflow on Kubernetes cluster like GCP, AWS or Azure etc.

-   **Kubeflow user interface**

There are many things that a Kubeflow UI includes, which can be listed below as:

1.  **Home**: A centralized dashboard for navigation between the Kubeflow components.
2.  **Pipelines**: A Kubeflow Pipelines dashboard.
3.  **Notebook**: There is a button for Jupyter notebooks.
4.  **Katib**: It is used for hyperparameter tuning.
5.  **Artifact Store:** It is used for tracking of artifact metadata.
6.  **Manage Contributors:** It is for sharing user access across namespaces in the Kubeflow deployment.

-   After that, you have implemented Kubeflow and Minikube on Ubuntu EC2 and accessed the Kubeflow dashboard.
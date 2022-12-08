# Summary

You completed the session on Kubernetes concepts. In this session, you learnt the following:

### Monolithic and Microservices Software Applications

-   Monolithic software application: If all the features are interdependent on and interconnected with each other, it means that all the services are on the same code space, and every feature is calling to a single server. This type of software application is called a monolithic application, which is built as a single unit.
-   Microservice software applications: In microservices software applications, everything is broken down into a collection of smaller services (conveniently named microservices).
-   Each microservice can be deployed independently of the rest of the application. For example, an online retailer could have one microservice for inventory management and another for controlling their shipping service.
-   The key point to remember is that before you can take advantage of Kubernetes, your applications need to have a microservice architecture.

Some of the benefits of using microservices are below:

1.  Microservices are highly maintainable and testable as each feature is independent of each other
2.  Each service is independently deployable using Docker and container
3.  Organised around business capabilities
4.  Each service can be owned by a small team

### Kubernetes Features

-   Kubernetes (commonly stylized as **K8s**) is an open-source container orchestration system for automating computer application deployment, scaling, and management.
-   Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation.
-   Kubernetes provides you with the following features-

1.  **Load balancing:** It provides the load balancing feature. Suppose a particular container is facing huge traffic. It distributes the traffic to other containers and maintains the stability of the deployment.
2.  **Storage orchestration:** Kubernetes allows you to automatically mount a storage system of your choice, such as local storages and public cloud providers.
3.  **Automated rollouts and rollbacks:** Kubernetes enables you to automate the creation of new containers for your deployment, remove existing containers and replace the existing containers with all the features of the older containers.
4.  **Automatic bin packing:** You can direct Kubernetes and provide a cluster of nodes that it can use to run containerised tasks. You can inform it regarding the amount of CPU and memory (RAM) needed by each container. It can fit containers onto your nodes to make the best use of your resources.
5.  **Self-healing:** Kubernetes restarts or replaces the containers that fail. It also kills containers that do not respond.

### Kubernetes architecture

-   Various levels under which Kubernetes works:

1.  **Cluster**: Kubernetes is a distributed system where there are masters nodes and worker nodes which collectively constitutes a cluster of nodes.
2.  **Master and worker nodes:** Master nodes are used to manage and coordinate various nodes of the cluster that run the containerised application. 
3.  **Pods**: Kubernetes pods are a group of containers that are deployed together on the same host or on the same worker node.
4.  **Control plane:** This is the centre of the Kubernetes cluster. The control plane manages and coordinates various nodes of the cluster that run the containerised application. This is also called the Kubernetes master node.

![Kubernetes Architecture](https://i.ibb.co/WFfFBxX/Kubernetes-Architecture.png)

-   **Control plane:** This is the centre of the Kubernetes cluster. The control plane manages and coordinates various nodes of the cluster that run the containerised application. In any production environment, the control plane usually runs across multiple computers, and a cluster usually runs multiple nodes, providing fault tolerance and high availability.

There are four major components of the control plane:

1.  **Kube- etcd:** It can be interpreted as a database which stores configuration data and information about the state of the cluster in key-value format. You can restore all the cluster components from etcd if anything wrong happens to your cluster.
2.  **Kube- Scheduler**: The main task of the scheduler is to schedule/assign pods to the available nodes. It is responsible for allocating resources like CPU/RAM to the pods.
3.  **API Server:** It acts as the gateway to the cluster. The API server is the front end of the control plane which handles internal and external requests. It is the main management point of the entire cluster.
4.  **Controller- Manager:** It notices when nodes go down and respond accordingly. It is important to maintain the correct number of pods for any running application. 

-   **Worker Node:** Any hardware which is capable of running the containers can be interpreted as a worker node. The group of such worker nodes is called a cluster and worker nodes are assigned workload and managed by the master node.

1.  **Pods**: Pods can be interpreted as the group of the containers which are used to run an application.
2.  **Kubelet**: It is used as a relay for the information to and from the control plane. It interacts with etcd to read and write configuration and information data about the state of the cluster.
3.  **Kube-** **proxy**: It constantly looks for new services and appropriately creates rules on each node to forward traffic to services and to the backend pods, respectively.
4.  **Kubectl**: It is a platform which is used to pass commands to the cluster. It provides the command-line interface to run commands for the Kubernetes cluster.

With this, you have completed the session on Kubernetes’ features and architecture. In the next session, you will get an end-to-end hands-on experience of using Kubernetes in AWS.
# What is Kubernetes

In the previous segment, you learnt that it is better to move from a monolithic application to microservices software applications. 

In this segment, you will learn about Kubernetes. Suppose you have a total of 500 Docker containers running. So, to manage all of these containers, you use Kubernetes.

Kubernetes (commonly stylised as **K8s**) is an open-source container orchestration system for automating computer application deployment, scaling and management.

It was designed by **Google**, and now, it is maintained by The **Cloud Native Computing Foundation.**

Let’s understand more about Kubernetes in the next video.

**VIDEO**

The official definition of Kubernetes is as follows: 

Kubernetes is a portable, extensible, open-source platform for managing containerised workloads and services that facilitates both declarative configuration and automation.

Suppose you have numerous containers running parallelly for an application. In the previous module, you learnt that Docker is better than a virtual machine, as it is faster and uses lesser resources. Hence, the Docker container is a better way to bundle the application. 

Now, those containers (that are running for an application) need to be managed, and it should ensure that there is no downtime for any of the containers. This means that if one container goes down, then a new container should get started corresponding to the older one. Kubernetes helps in facilitating the same.
  
You can gain a better understanding of Kubernetes from its official website, which is given below.  
 
[Kubernetes_official_site](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)

In the next video, you will learn about the various features of the Kubernetes.

**VIDEO**

You need to keep in mind that Docker and Kubernetes are not alternative to each other, and many people get confused with this. Dockers are used to creating containers, and Kubernetes is used to manage the containers. 

Kubernetes provides you with the following features:

**Note**: These features have been taken from the [Kubernetes official website](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/):

-   **Load balancing:** It provides the load balancing feature. Suppose a particular container is facing huge traffic. It distributes the traffic to other containers and maintains the stability of the deployment.
-   **Storage orchestration:** Kubernetes allows you to automatically mount a storage system of your choice, such as local storages and public cloud providers.
-   **Automated rollouts and rollbacks:** Kubernetes enables you to automate the creation of new containers for your deployment, remove existing containers and replace the existing containers with all the features of the older containers.
-   **Automatic bin packing:** You can direct Kubernetes and provide a cluster of nodes that it can use to run containerised tasks. You can inform it regarding the amount of CPU and memory (RAM) needed by each container. Kubernetes can fit containers onto your nodes to make the best use of your resources.
-   **Self-healing:** Kubernetes restarts or replaces the containers that fail. It also kills containers that do not respond.

Kubernetes runs at the container level, not at the hardware level. It provides features such as deployment, scaling and load balancing.

In the next segment, you will learn about Kubernetes’ architecture.  

#### Container orchestration

Qn: What is container orchestration?

- Container orchestration simply refers to the load balancing among the containers.

- Container orchestration means every service of a whole application is divided into multiple containers.

- Container orchestration refers to the ability to communicate among containers of multiple services of a microservice software application to run the whole application as a single unit.

Ans: C.

#### Kubernetes

Qn: Which of the following statements describe the relation between Kubernetes and Docker?

- Docker creates containers and these multiple containers communicate using Kubernetes.

- Kubernetes does not allocate memory to each container according to their requirement but only manage them in terms of restarting or replacing the containers.

- Kubernetes is a container orchestration tool.

- If a particular container is getting huge data then Kubernetes does not balance a load of this container as it is not the work of the Kubernetes.

Ans: A & C. *Kubernetes is a container management tool which is responsible for container deployment, scaling & descaling of containers & load balancing.*

Qn: Kubernetes is created by Cloud Native Computing Foundation and now it is maintained by Google.

- True

- False

Ans: B. *Kubernetes is created by Google and now it is maintained by the Cloud Native Computing Foundation.*

# Kubernetes Architecture- II

In the previous segment, you gained a broad understanding of the working of a Kubernetes cluster. In this segment, you will get a better and deeper idea of Kubernetes’ architecture.

Let’s start the segment with this video.

**VIDEO**

Let’s first try to understand the concept of a control plane or Kubernetes master.

![Kubernetes Architecture](https://i.ibb.co/WFfFBxX/Kubernetes-Architecture.png)

**Control plane:** This is the centre of the Kubernetes cluster. The control plane manages and coordinates various nodes of the cluster that run the containerised application. In any production environment, the control plane usually runs across multiple computers, and a cluster consists of multiple nodes, providing fault tolerance and high availability.

There are four major components of the control plane:

1.  **Kube- etcd:** This is an extremely important component of the Kubernetes cluster, as it stores the configuration data and information about the state of the cluster. It can be interpreted as a database that stores the cluster information in the key-value format. You can restore all the cluster components from etcd if anything wrong happens to your cluster.
2.  **Kube- Scheduler:** The main task of the scheduler is to schedule/assign pods to the available nodes. It is responsible for workload utilisation and allocates resources such as CPU/RAM to the pods and then schedules the pods to the appropriate worker node. In other words, it checks the health of the cluster. 
3.  **API Server:** It acts as the gateway to the cluster. It is the front end of the control plane that handles internal and external requests. It is the main management point of the entire cluster. 
4.  **Controller- Manager:** It notices when nodes go down and respond accordingly. It is important to maintain the correct number of pods for any running application. 

You can refer to the additional links given at the end of the segment to understand more about various components of the control plane.

  
In the next video, you will learn about worker nodes and containers.

**VIDEO**

Let’s understand the structure of the worker nodes:

**Worker Node:** Any hardware that is capable of running the containers can be interpreted as a worker node. A group of such worker nodes is called a cluster. Worker nodes are assigned workload and are managed by the master node.

1.  **Pods**: Pods can be interpreted as a group of the containers that are used to run an application.
2.  **Kubelet**: It is used as a relay for the information to and from the control plane to the worker node. It interacts with etcd to read and write configuration and information data about the state of the cluster. It ensures that all the containers are running in pods, and when the control plane needs some information about the nodes, kubelet provides it.
3.  **Kube- proxy**: It constantly looks for new services and appropriately creates rules on each node to forward traffic to services and to the pods, respectively. kube-proxy maintains network rules on nodes. These network rules allow network communication to your pods from network sessions inside or outside of your cluster.

Let’s gain an understanding of **kubectl**-

It is a platform that is used to pass commands to the cluster. It provides the command-line interface to run commands for the Kubernetes cluster. Using kubectl, you interact with the API server of the control plane and ultimately interact with the Kubernetes cluster.

You have understood the end-to-end architecture of Kubernetes.

In the below additional links, you can get more idea about the Kubernetes architecture.

**Additional Resources:**

[Kubernetes architecture-I](https://kubernetes.io/docs/concepts/overview/components/)

[Kubernetes architecture-II](https://www.educative.io/edpresso/the-kubernetes-architecture-simplified?affiliate_id=5082902844932096&utm_source=google&utm_medium=cpc&utm_campaign=platform2&utm_content=ad-1-dynamic&gclid=Cj0KCQjw-uH6BRDQARIsAI3I-Udwn0zRNV5PTMamBjbYQfY9iE9G_lm9h9MyzxyyYpAMfDjKpN-SKSUaAtqLEALw_wcB)

#### Kubernetes

Qn: Which of the following statements are true regarding pods? Multiple options may be correct.

- Pods are nothing but another name of the worker nodes.

- Pods are the group of the containers.

- The containers in the same pod share a local network and the same resources, allowing them to easily communicate with other containers in the same pod.

- Pods are used to interact with the control plane and provide necessary information to the control plane about the cluster.

Ans: B & C. *Pods are the collection of containers that runs inside a worker node.*

Qn: What of the following is true about kubectl and kubelet?

- Kubectl is used as a relay between the master node and worker node to exchange the information.

- Kubelet is nothing but a CLI to interact with Kubernetes.

- Kubectl is the component of the control plane and stores the configuration data and information about the state of the cluster.

- Kubelet is used as a relay between the master node and worker node to exchange the information.

Ans: D.

Qn: Which of the following is the correct match for control plane and worker node components?

- Etcd, kubelet are the components of the control plane.

- API server, schedular and kube- proxy are the components of the control plane.

- Pods, kubelet and kube-proxy are the components of the worker nodes.

- Pods, kubectl and controller- manager are the components of the worker nodes.

Ans: C.

**Comprehension:**

Suppose an organisation has four managing directors (MD-1, MD-2, MD-3 and MD-4). 

There are multiple departments with their respective heads who report to the managing directors. Each department consists of multiple teams. There is a job role in each department that is to constantly look into new R&D projects and assign guidelines to the team members about those projects.

Suppose each managing director has their own role that can be defined in the following way:

-   **MD-1:** He is responsible for maintaining the entire status of the organisation that is related to workforce, financial status, revenue generated, profit of the company and collaboration of the company with other universities and organisations. He keeps track of the team status that is given by the respective heads of the departments.
-   **MD-2:** His main task is to assign workforce and allocate finances to the respective teams and departments.
-   **MD-3:** His main task is to determine the department that is not working efficiently, and he is responsible for creating the team inside a particular department to get the job done on specific projects.  
    **MD-4:** She is the front face of the organisation and deals with the other managing directors. She is the main managing point of the organisation.

Now based on the learnings from the Kubernetes, draw the analogy and answer the following questions.

#### Kubernetes

Qn: Which of the managing directors is analogous to the Scheduler?

- MD-1

- MD-2

- MD-3

- MD-4

Ans:B. *MD-2 is analogous to the scheduler.*

Qn: The head of each department can be treated as _________ in the Kubernetes architecture.

- Kubelet

- Pods

- Kube-proxy

- Containers

Ans: A. *This is the correct option as the head of each department is responsible to convey the status of the department to the managing directors. And he is also responsible that each employee is working efficiently and updates the status to the managing directors’ team about that.*

Qn: What is analogous to the pods in Kubernetes?

- Department

- Head of the department

- Each team in the respective departments

- Managing directors

Ans: C.

Qn: Will it be correct to say that each employee is analogous to the container in Kubernetes?

- Yes

- No

Ans: A. *Each team can be treated as pods and we know that pods are the group of the containers which is running the services and hence, each employee can be treated as the containers.*

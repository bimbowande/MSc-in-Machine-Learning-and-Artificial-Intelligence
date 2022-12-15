# Kubernetes Architecture - I

In the previous segment, you understood the concept of Kubernetes and learnt about its features. 

In the next video, let’s understand the architecture of Kubernetes in the next video.

**VIDEO**

So, let’s take a look at the different levels under which Kubernetes works:

1.  **Cluster**: Kubernetes is a distributed system that includes master nodes and worker nodes, which collectively constitute a cluster of nodes.
2.  **Master and worker nodes:** Master nodes are used to manage and coordinate various nodes of the cluster that run the containerised application. 
3.  **Pods**: Kubernetes pods are a group of containers that are deployed together on the same host or the same worker node.
4.  **Control plane:** This is the centre of the Kubernetes cluster. The control plane manages and coordinates various nodes of the cluster that run the containerised application. This is also called the Kubernetes master node.

You will understand more about them in the next segment.

![Kubernetes Architecture](https://i.ibb.co/WFfFBxX/Kubernetes-Architecture.png)

The whole Kubernetes architecture works on the master and worker node cluster architecture.

A Kubernetes environment consists of the following three broad components:

1.  **Control plane (Kubernetes master node):** The control plane manages and coordinates various nodes of the cluster. It runs on a master node to manage all the worker nodes of the cluster.
2.  **etcd**: It is a distributed storage system for storing the cluster state. It stores the entire state of the cluster such as configuration, specifications and the statuses of the running workloads.
3.  **Worker nodes:** Nodes are machines that run containers and are managed by the Kubernetes master nodes.

In the next segment, you will gain a better understanding of Kubernetes’ architecture.
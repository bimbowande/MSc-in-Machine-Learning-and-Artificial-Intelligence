# What is Minikube

You have already learnt about the Kubernetes in the previous session. You are aware that Kubernetes is a container orchestration tool. There are many containers which run for an application, need to be managed and it should ensure that there is no downtime for any of the containers. Which means that if one container goes down then a new container should be started corresponding to the older container. 

The Kubernetes is the solution, which manages all the containers.

You have already deployed the Kubernetes cluster on AWS. What if you want to create the Kubernetes cluster on your local for testing or learning purposes.

Let’s listen to Abhay in the next video.

**VIDEO**

![Minikube Architechture](https://i.ibb.co/wR3rNdp/Minikube-Architechture.png)

So, the Minikube is a single-node Kubernetes cluster that is deployed using a virtual machine on your local machine. It is used to learn Kubernetes. Actual production systems use Kubernetes clusters with more number of master nodes and the worker nodes to achieve high availability.

Let’s listen to Abhay explain how you can interact with the cluster in case of Minikube.

**VIDEO**

So, you are already aware that to interact with the Kubernetes cluster you require kubectl. The interaction point through which we interact with the Kubernetes cluster is the API server of the control plane. 

In the next segment, you will learn about Kubeflow.

#### Minikube and Kubeflow

Qn: Check whether the following statement is true or not: *Minikube is used as the learning purpose of the Kubernetes and it is deployed on a single node cluster may be in your own local machine.*

- True

- False

Ans:A. *Minikube is meant to deploy on local and it is a single-node cluster which is used as Kubernetes learning.*

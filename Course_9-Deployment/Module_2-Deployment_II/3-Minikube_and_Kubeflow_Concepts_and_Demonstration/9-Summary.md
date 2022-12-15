# Summary

You have completed the session on conceptual understanding of Minikube and Kubeflow.

Let’s summarise the whole session in the following way:

-   **Minikube**

Minikube is a single-node Kubernetes cluster that is deployed using a virtual machine on your local machine. It is used to learn Kubernetes. Actual production systems use Kubernetes clusters with more number of master nodes and the worker nodes to achieve high availability.

So, you are already aware that to interact with the Kubernetes cluster you require kubectl. The interaction point through which we interact with the Kubernetes cluster is the API server of the control plane. 

![Minikube Architechture](https://i.ibb.co/wR3rNdp/Minikube-Architechture.png)

-   **Kubeflow: Workflow**

Kubeflow is an ML platform, which is designed to use ML pipelines to orchestrate complicated workflows running on Kubernetes clusters.

You can divide the whole Kubeflow overview into three parts:

1.  **ML tools:** You have a Kubeflow UI interface (You will have hands-on using Kubeflow interface in the further segments) which provides various ML tools which are required for your workflow like PyTorch, TensorFlow and XGBoost etc.
2.  **Kubeflow applications:** There are various applications that Kubefloe provides at its UI interface.
3.  **Platform/clouds:** There are various clouds services where you can deploy your Kubeflow on Kubernetes cluster like GCP, AWS or Azure etc.

You can refer to the following link to understand the conceptual overview of the Kubeflow:  
[Kubeflow conceptual overview](https://www.kubeflow.org/docs/started/kubeflow-overview/)  
 
-   **Kubeflow user interface**

So, there are many things that a Kubeflow UI includes, which can be listed below as:

1.  **Home:** A centralized dashboard for navigation between the Kubeflow components.
2.  **Pipelines:** A Kubeflow Pipelines dashboard.
3.  **Notebook:** There is a button for Jupyter notebooks.
4.  **Katib**: It is used for hyperparameter tuning.
5.  **Artifact Store:** It is used for tracking of artifact metadata.
6.  **Manage Contributors:** It is for sharing user access across namespaces in the Kubeflow deployment.

The Kubelfow UI looks like below:

![Kubelfow UI](https://i.ibb.co/sF3bzPL/Kubelfow-UI.png)

-   **Kubeflow demonstration**

You have learnt to deploy Minikube and Kubeflow on Ubuntu EC2 using a group of commands.

In this way, you have completed the session on Kubeflow, Minikube and its demonstration.
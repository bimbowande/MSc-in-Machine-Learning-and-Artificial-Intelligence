# Kubeflow Workflow

You have seen in the previous segment that Kubeflow is an open-source Kubernetes platform for developing, orchestrating, deploying and running scalable and portable ML workloads.

Let’s understand the conceptual overview of the Kubeflow in the next video.

**VIDEO**

Let’s try to understand the conceptual overview of the Kubeflow.

![Kubeflow Overview](https://i.ibb.co/nMxHJsQ/Kubeflow-Overview.png)

Image source: **https://www.kubeflow.org/docs/started/kubeflow-overview/**

You can divide the whole Kubeflow overview into three parts:

-   **ML tools:** You have a Kubeflow UI (You will have hands-on using Kubeflow interface in the further segments) which provides various ML tools which are required for your workflow like PyTorch, TensorFlow and XGBoost etc.
-   **Kubeflow applications:** There are various applications that Kubeflow provides at its UI.
-   **Platform/clouds:** There are various clouds services where you can deploy your Kubeflow on Kubernetes cluster like GCP, AWS or Azure etc.

You can refer to the following link to understand the conceptual overview of the Kubeflow:  
[Kubeflow conceptual overview](https://www.kubeflow.org/docs/started/kubeflow-overview/)

Deployment of an ML model is an iterative process. You have to look after all your outputs at the various stages of the ML workflow and apply changes to make sure that the ML model is working as per the results that you need to obtain.  

[![ML Workflow](https://i.ibb.co/4TM9YcK/ML-Workflow.png)](https://www.kubeflow.org/docs/started/kubeflow-overview/)

Image source: **https://www.kubeflow.org/docs/started/kubeflow-overview/**

You can divide the whole ML deployment process into two parts:

-   **Experiment phase:** In this phase, you build your ML model and start with collecting and analysing the data, choose an appropriate ML algorithm and perform some experiments like training and data modelling and then tune the model’s hyperparameters to get the desired results. You iteratively perform this process until you won’t get the desired results from your ML model.
-   **Production phase:** In the production phase, you basically serve the model for online prediction and monitor the ML model performance. 

You have seen many blocks (in the experiment phase and in the production phase) in the above diagram which solves different purposes to deploy an ML model and make it available online. 

There are various tools and applications on Kubeflow which can handle the different blocks on the above diagram. You will get a better understanding of this in the next video.

**VIDEO**

So, suppose you are doing ML model experiment and deployment using Kubeflow then you have various tools which are offered by Kubeflow to perform experimental phase like PyTorch, Jupyter notebook, TensorFlow, scikit-learn etc. for the corresponding building blocks, which is shown below:

![Kubeflow Phases 1](https://i.ibb.co/jM7Rbf1/Kubeflow-Phases-1.png)

Image source: **https://www.kubeflow.org/docs/started/kubeflow-overview/**

In a similar fashion, there are various tools with Kubeflow, where you can run the production phase of the ML model.

![Kubeflow Phases 2](https://i.ibb.co/qD2gTGH/Kubeflow-Phases-2.png)

Image source: **https://www.kubeflow.org/docs/started/kubeflow-overview/**

So, you can develop an end to end ML pipeline using Kubeflow and Kubernetes. You can understand it in a better way in the next video:

**VIDEO**

In the next segment, you will see how Kubeflow UI looks like.

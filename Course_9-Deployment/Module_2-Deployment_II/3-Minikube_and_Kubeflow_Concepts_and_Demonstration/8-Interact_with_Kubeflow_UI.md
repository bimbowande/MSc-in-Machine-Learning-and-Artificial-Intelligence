# Interact with Kubeflow UI

In the previous segment, you have accessed the Kubeflow UI through EC2 instance. Now in this segment, you will see how you can interact with the dashboard and access Jupyter notebook. 

Note that the Kubeflow or similar tools like ML flow are meant to deploy **deep learning models** but here we will take a simple example to learn the working of the Kubeflow dashboard.

**VIDEO**

Following are the summary of steps to access the notebook server which you need to follow:

1.  Set up your Kubeflow deployment using EC2 and open the Kubeflow dashboard UI.
2.  Click on the **Notebook Servers** in the left-hand panel of the Kubeflow UI.
3.  Choose the appropriate **namespace** related to your Kubeflow profile.
4.  Click on the **New Server to** create a notebook server.
5.  When the notebook server provisioning is complete, click **Connect**.
6.  Click on the Upload button to upload an existing notebook, or click **New** to create an empty notebook.

In the next step, you will be starting the setup the notebook on Kubeflow.

**VIDEO**

So, in the above, you have created a notebook server. 

  
In the next video, you will run the Jupyter notebook on the Kubelfow dashboard. Before that, you have been provided with a simple iris dataset which you can upload on notebook and perform the basic implementation.

Download [Iris Notebook](iris-Notebook.ipynb)

**VIDEO**

You have run the Iris dataset notebook on notebook on Kubeflow dashboard.

In this way, you have seen that you can run the notebook server on Kubeflow. You are already aware that Kubeflow is meant to deploy deep learning models and you can create your own ML pipelines to deploy. 

The Ml pipeline deployment part is not covered in this module as this is out of the scope of this program.

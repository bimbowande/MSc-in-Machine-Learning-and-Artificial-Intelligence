# Define and Create the Kubernetes Cluster

In the previous segment, you learnt how to create an S3 bucket and a private hosted zone and also configured environment variables. In this segment, you will learn how to create a Kubernetes cluster.

Let’s watch the next video to learn about the commands that are required for creating a Kubernetes cluster.

**VIDEO**

Let’s try to understand the Kubernetes Cluster definition:

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

It is important to understand that the above-mentioned commands are not used for creating the Kubernetes cluster; they are used for defining the cluster. Using this definition, you will create a cluster through the ‘update cluster’ command.

-   **state:** The state is the S3 bucket location where all the states of the nodes are storing and updating according to the further changes in the cluster.
-   **node-count:** This is the count of the worker nodes that you are creating initially, which is 2 in this case. 
-   **master-size:** This is the type of the master node, which is ‘t2.micro’ in this case.
-   **node-size:** This is the type of the worker node, which is ‘t2.micro’ in this case.
-   **zones:** This is the zone of the AWS region whose data centres you are using. Let’s go through [this](https://cloudacademy.com/blog/aws-regions-and-availability-zones-the-simplest-explanation-you-will-ever-find-around/#:~:text=An%20AWS%20Availability%20Zone%20(AZ,data%20centers%20%E2%80%94%20within%20a%20region.) link to understand more about the zones. 
-   **name:** This is the name of the Kubernetes cluster.
-   **dns:** This is the hosted zone that we have created using Route53 and this private in this case.
-   **master-count:** This is the count of the master nodes that you are creating initially, which is 1 in this case. 

Now, let’s create a Kubernetes cluster using the below command.

```shell
kops update cluster --yes
```

With this, you have created a Kubernetes cluster with 1 master node and 2 worker nodes.

If you use the validate cluster command, it will show you an error message because the cluster is not ready yet. You need to wait for a few minutes. In the next video, you will learn how to validate the cluster.

**VIDEO**

You can use the following command to validate the cluster.

```shell
kops validate cluster
```

By validating the cluster, you can check the status of the nodes and the total number and types of the master and the worker nodes.

You can delete the cluster after completing all the steps. Note that **it is extremely important that you delete the cluster and remove all the IAM roles and EC2 instances at the end of the demonstration** because it costs a lot to keep the cluster in the running state. You can use the following command to delete the cluster:

```shell
kops delete cluster --yes
```

You can change the number of nodes and masters nodes using the following commands:  
 

```shell
kops edit ig nodes change minSize and maxSize to 0
kops get ig- to get master node name
kops edit ig - change min and max size to 0
kops update cluster --yes
```

  
But for now, you do not need to delete the cluster or change the number of nodes because there are a few steps you need to complete.

#### Kops

Which of the following is correct when you write the following lines of command in EC2 CLI? Multiple options can be correct.

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

- This is the set of commands that creates a Kubernetes cluster.

- This set of commands will not create the Kubernetes cluster but this is just a definition of the cluster that you want to create.

- The line “--state=${KOPS_STATE_STORE} \ ” defines the S3 bucket location where all the states of the nodes are storing and updating according to the further changes in the cluster.

- The line “--state=${KOPS_STATE_STORE} \ ” defines the state of the nodes in the cluster.

Ans: B & C. *The given set of commands is only the definition of the Kubernetes cluster.*

Qn: Which of the following commands is used to create the Kubernetes cluster?

- 
```shell
kops validate cluster
```

- 
```shell
kops update cluster --yes
```

- 
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

Ans: B. *This command is used to create the Kubernetes cluster after defining the cluster.*

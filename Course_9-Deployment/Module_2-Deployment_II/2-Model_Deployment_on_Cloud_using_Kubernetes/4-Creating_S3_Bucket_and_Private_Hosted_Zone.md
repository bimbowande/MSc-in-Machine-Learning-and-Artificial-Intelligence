# Creating S3 Bucket and Private Hosted Zone

In the previous segment, you learnt how to install Kops and kubectl on EC2. In this segment, you will learn how to create an S3 bucket and a private hosted zone and key.

Let’s watch the next video to learn how to do this.

**VIDEO**

As you learnt in the video above, the next step involves creating an S3 bucket. You can use the following command to do this(note: You need to choose a bucket name that is **unique** across all AWS accounts):

```shell
aws s3 mb s3://kops-bucket.in.k8s --region us-east-1
```

Now let’s understand why it is important to create an S3 bucket.

In order to manage all the clusters that have been created, Kops needs to track all the configurations and the state of the cluster and for this, Kops needs storage space to store all the information related to the cluster state.

Kops needs to store information such as the number of nodes, instance type of each node and the Kubernetes version. The information related to the state of the cluster is stored during the initial cluster creation process. Any other changes to the cluster are updated to this storage later. To keep track of such information, Kops uses S3 storage.

In the next video, you will learn how to create a private hosted zone and key.  
 
**VIDEO**

In the video above, you learnt how to create a private hosted zone and key.

Kops will require a DNS name when you try to reach the Kubernetes API server from the clients.

As you already know, the master node communicates with all the worker nodes. The master node also needs to communicate with the etcd server, which is a storage system that stores all the configuration data and information about the state of the cluster. 

Also, kubectl, the CLI tool, needs to communicate with the master node.

For all these communication purposes, AWS provides the Route 53 hosted zone.

Let’s try to understand how the hosted zone works.

You must be aware of DNS (Domain Name System), which is a global system that translates human-readable names, such as upgrad.com and amazon.com, into the numeric IP addresses (for example, 192.1.1.1) of the related server. These IP addresses are used by computers to connect with each other.

Amazon Route 53 provides an easily available and highly scalable DNS and domain name registration. A hosted zone acts as a container for records. These records contain information about how you want to route the traffic for a specific domain (for example, upgrad.com) and its subdomains (for example, abc.upgrad.com or xyz.upgrad.com).

You can refer to the AWS documentation links provided below to learn more about the hosted zone and Route53.  
 
[Hosted zone and route53-I](https://aws.amazon.com/route53/faqs/)

[Hosted zone and route53-II](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-working-with.html)

The next step involves configuring environment variables. To do this, you can use the following commands:

a. Open .bashrc file 

```shell
vi ~/.bashrc
```

b. Add the following content into .bashrc. Note: You can choose any arbitrary name for the cluster, but you need to ensure that the S3 bucket name matches the one that you created earlier.

```shell
export KOPS_CLUSTER_NAME=test-cluster.in
export KOPS_STATE_STORE=s3://kops-bucket.in.k8s
```

c. Then run the following command to reflect the variables added to .bashrc

```shell
source ~/.bashrc
```

d. Create an SSH key pair: This key pair is used for SSH into Kubernetes cluster

```shell
ssh-keygen
```

#### Kops

Qn: Which of the following statements are true regarding the S3 bucket creation while running Kops on AWS? Multiple options may be correct.

- S3 bucket is created to store the information of the cluster like the number of nodes and instance type.

- This bucket is only updated at the starting of the cluster creation only and it does not track the subsequent changes to the cluster. 

- It is recommended to apply versioning to this S3 bucket because if you lost this bucket then you can retrieve all the data from the version of this bucket.

Ans: A & C. *It is recommended to version the S3 bucket to restore all the data from the version bucket. You can enable versioning using the AWS CLI as shown below:*

```shell
aws s3api put-bucket-versioning --bucket BUCKET_NAME --versioning-configuration Status=Enable
```

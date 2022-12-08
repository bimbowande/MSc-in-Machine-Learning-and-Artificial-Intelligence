# Setting up EC2 Instance with Kops and kubectl

In the previous segment, you learnt the difference between EKS and Kops. Now let’s use Kops on AWS.

First, let’s understand how kubectl actually works. Kubectl refers to the Kubernetes command-line tool. It is used for deploying applications, inspecting and managing cluster resources and viewing the logs of the Kubernetes cluster.

Let’s watch the next video and set up instances and IAM roles on AWS.

**VIDEO**

The whole process involves the following steps:

-   Launch Linux EC2 instance on AWS. Note: In the demonstration, Abhay launched **Amazon Linux 2 AMI (HVM), SSD Volume Type EC2 instance.**
-   Create an IAM role and attach it to the EC2 instance. Note that Kops needs the following permissions to access:

1.  S3
2.  EC2
3.  VPC
4.  Route53
5.  Autoscaling
6.  Etc.

The document for installing and configuring the end-to-end setup of Kops on AWS is attached below.

Download [Kops on AWS-User Guide](Docs/Amazon_Web_Services/Kops_on_AWS.pdf)

In the next video, you will learn to install the Kops and kubectl on the EC2.

**VIDEO**

Let’s follow the below-mentioned commands to install Kops and kubectl (these steps are also mentioned in the document provided above).

-   **Install Kops on EC2:**

**a. Download kops binary:** Download the kops binary from the link provided below. Binaries are the compiled code that allows a program to be installed without the need for compiling the source code.

```shell
curl -LO https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag_name | cut -d '"' -f 4)/kops-linux-amd64
```

**b. Execute permissions for binary**

```shell
chmod +x kops-linux-amd64
```

**c. Move binary to usr/local/bin so the command is in the path**

```shell
sudo mv kops-linux-amd64 /usr/local/bin/kops
```

**d. Check installation version of kops**

```shell
kops version
```

-   **Install kubectl on EC2:**

**a. Download kubectl binary**

```shell
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```

**b. Execute permissions for binary**

```shell
chmod +x ./kubectl
```

**c. Move binary to usr/local/bin so the command is in the path**

```shell
sudo mv ./kubectl /usr/local/bin/kubectl
```

In the next segment, you will learn about the next steps for installing and configuring the end-to-end setup of Kops on AWS.
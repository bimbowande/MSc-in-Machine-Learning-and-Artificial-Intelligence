# Amazon EKS Vs Kops

In this session, you will learn how to deploy a Kubernetes cluster on AWS. There are two major methods to deploy a Kubernetes cluster on AWS, which are as follows:

-   Amazon EKS: Elastic Kubernetes Service
-   Kops: Kubernetes operations

Let’s watch the upcoming video to understand the difference between these two methods.

**VIDEO**

Amazon EKS and Kops can be summarised as follows:

-   **Amazon EKS (Elastic Kubernetes Service):** EKS is a managed Kubernetes service provided by AWS. Using EKS, you can run Kubernetes on AWS without installing, operating and maintaining the Kubernetes control plane. EKS is an easily available and highly secure Kubernetes service.

EKS is a relatively new service and, hence, is not well-documented on the internet. Also, setting up a cluster with EKS is a bit more complicated than doing the same with Kops.

-   **Kops (Kubernetes Operations):** Kops is an open-source project that can be used for setting up a Kubernetes cluster on cloud services such as AWS and GCP. Kops is older than EKS, and hence, many industries use Kops for business deployment. It is a CLI tool that is known as the kubectl way of creating the clusters.

In the subsequent segments, you will get hands-on experience of using Kops on AWS.

**Additional links:**  
[EKS vs Kops](https://www.bluematador.com/blog/kubernetes-on-aws-eks-vs-kops)

#### EKS vs Kops

Qn: Which year did the Kops and Amazon EKS launch?

- Kops: 2018, EKS: 2016

- Kops: 2016, EKS: 2018

- Both in the same year i.e. 2018

- Both in the same year i.e. 2016

Ans: B. *Kops is older than the Amazon EKS and hence, it is more mature and many documentations are available on the internet.*

Qn: Which of the following statement is correct regarding EKS and Kops? 

- Kops is the managed service provided by AWS.

- EKS is the command-line interface tool where using kubectl CLI you can direct the cluster and manage the cluster.

- EKS can be set up on GCP.

- Kops can be set up in the Kubernetes cluster on the clouds like AWS or GCP.

Ans: D. *Kops is an open-source project to set up the Kubernetes cluster on any cloud like AWS or GCP.*

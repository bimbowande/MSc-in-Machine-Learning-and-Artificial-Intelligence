# Installing Docker and Minikube on EC2

Let’s start the session on the installation of Minikube and Kubeflow. This session will cover the installation of Minikube and Kubeflow in a single node Ubuntu system. You are already aware that the Minikube provides a single-node Kubernetes cluster that is good for development and testing purposes.

Let’s listen to Abhay first.

**VIDEO**

The guide covers the following topics:

-   Installation of docker-community edition (docker-ce), kubectl, and Minikube.
-   Installation of Kubeflow on ubuntu machine.
-   Launch the Kubeflow central dashboard.

Following are the prerequisites that are required to install Kubeflow and Minikube:

-   Ubuntu 18 machine with min 8 cores, 16GB RAM and 250GB storage.
-   Root privileges on a Ubuntu machine.

So, you have seen that Abhay has created an Ubuntu instance and you can follow an end to end user guide which is mentioned below:

Download [Kubeflow on EC2- User Guide](Docs/Amazon_Web_Services/Kubeflow_on_EC2.pdf)

In the next video, you will learn to install Docker, kubectl and Minikube on EC2 instances.

**VIDEO**

Once, you have logged into your Ubuntu instance, then you need to follow the following steps to install the Docker. It is very important to note that, to install Docker, you have to be at the root. So paste the following command to enter into the root user.

```shell
sudo -i
```

-   Next, you need to install Docker CE using the following commands:

```shell
apt-get update
apt-get install -y apt-transport-https ca-certificates curl software-properties-common
```

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add -
add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
apt-get update
apt-get install docker-ce docker-ce-cli containerd.io
```

-   Let’s verify the Docker installation:

```shell
docker run hello-world
```

-   Once, you have installed Docker, the next is to Install kubectl:

```shell
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.15.0/bin/linux/amd64/kubectl
chmod +x ./kubectl
mv ./kubectl /usr/local/bin/kubectl
```

-   Next, you need to install Minikube:

```shell
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.2.0/minikube-linux-amd64
```

-   Let’s move the Minikube to /usr/local/bin:

```shell
chmod +x minikube
cp minikube /usr/local/bin/
rm minikube
```

In this way, you have completed the installation of Docker, Minikube and kubectl on your Ubuntu EC2 instance.

In the next segment, you will learn to install Kubeflow on EC2.
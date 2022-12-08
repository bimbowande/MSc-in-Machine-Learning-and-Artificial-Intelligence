# Installing Kubeflow on Minikube

In the previous segment, you have learnt to install Docker, Minikube and kubectl on an ubuntu EC2 instance. Now, in this segment, you will learn to install Kubeflow.

Let’s listen to Abhay first.

**VIDEO**

-   You need to start the Minikube first using the following commands:

```shell
minikube start --vm-driver=none --cpus 4 --memory 20000 --disk-size=60g --extra-config=apiserver.authorization-mode=RBAC --extra-config=kubelet.resolv-conf=/run/systemd/resolve/resolv.conf --extra-config kubeadm.ignore-preflight-errors=SystemVerification
```
Now, let’s perform the Installation of Kubeflow on Minikube:

-   First, you need to create a folder for Kubeflow installation using the following command.

```shell
mkdir -p /root/kubeflow/v1.0
cd /root/kubeflow/v1.0
```

-   The next is the installation of kfctl (Kubeflow command line interface) which is used to install and configure Kubeflow. You can download the tar file of kfctl using wget command.

```shell
wget https://github.com/kubeflow/kfctl/releases/download/v1.1.0/kfctl_v1.1.0-0-g9a3621e_linux.tar.gz
```

-   In the next step, you unpack the tar file that you have downloaded from the above commands.

```shell
tar xvf kfctl_v1.1.0-0-g9a3621e_linux.tar.gz
```

-   Firstly you need to export the path of the directory where you have downloaded the Kubelfow.

```shell
export PATH=$PATH:/root/kubeflow/v1.0
```

-   Set the KF_NAME to the name of your Kubeflow deployment. You also use this value as a directory name when creating your configuration directory.

```shell
export KF_NAME=my-kubeflow
```

-   Next, you need to set the path of the base directory where you want to store one or more Kubeflow deployments.

```shell
export BASE_DIR=/root/kubeflow/v1.0
```

-   Then set the Kubeflow application directory for this deployment.

```shell
export KF_DIR=${BASE_DIR}/${KF_NAME}
```

-   In the next part you need to set the URI of the configuration file to use when deploying Kubeflow and create the Kubeflow configurations.

```shell
export CONFIG_URI="https://raw.githubusercontent.com/kubeflow/manifests/v1.0-branch/kfdef/kfctl_k8s_istio.v1.0.2.yaml"
```

-   Create the directory you want to store deployment

```shell
mkdir -p ${KF_DIR}
cd ${KF_DIR}
kfctl apply -V -f ${CONFIG_URI}
```

-   You can get the Kubeflow running status using the following command:

```shell
kubectl get pod -n kubeflow
```

Now, in the next video, you will be able to see the final Kubeflow dashboard.

**VIDEO**

To launch the Kubeflow dashboard, you need to perform the following steps:

-   Launch of Kubeflow central dashboard:

```shell
export INGRESS_HOST=$(minikube ip)
export INGRESS_PORT=$(kubectl -n istio-system get service istio-ingressgateway -o jsonpath='{.spec.ports[?(@.name=="http2")].nodePort}')
```

-   You can get the ingress Host and Port using the following command:

```shell
echo $INGRESS_HOST
```

```shell
echo $INGRESS_PORT
```

Then you can access the Kubeflow dashboard in a web browser:

_**http://<PUBLIC_LINK_OF_EC2>:<INGRESS_PORT>**_

In this way, you have completed the Kubeflow installation and dashboard access. In the next segment, you will have a demonstration on Notebook Server on Kubeflow dashboard.
# Expose the Web Application with UI

In the previous segment, you used Kubernetes and deployed the Iris ML model on the Jupyter Notebook.

In this segment, you will expose the web application with a user interface through which users can access the ML model.

**VIDEO**

You have been given all related files in the below folder:

-   requirements.txt
-   Dockerfile
-   server.py
-   svm.pckl
-   Index.html

Download [Iris Code for UI](deploy-code.zip)

You need to add such files into a directory named **deploy-ml-flask** on EC2.

In the next video, you will follow the same steps that you completed in the previous segments to build and push the Docker image into ECR.

**VIDEO**

-   Let’s restart Docker.

```shell
sudo service docker restart
```

-   Build an iris application

```shell
sudo docker build -t iris-app:v1 .
```

Validate that the image has been created by running sudo docker images again

-   Authenticate to container Registry AWS

```shell
sudo $(aws ecr get-login --no-include-email --region us-east-1)
```

Copy the url from ECR

![Copy URL Resources](https://i.ibb.co/9c0yMzD/Copy-URL-Resources.png)

```shell
sudo docker tag iris-app:v1 177300670946.dkr.ecr.us-east-1.amazonaws.com/test-awsecr:v1
```

Now that you have tagged it, the whole thing needs to be pushed. Hence, we will use sudo docker push followed by the URL.

```shell
sudo docker push 177300670946.dkr.ecr.us-east-1.amazonaws.com/test-awsecr:v1
```

Once this is done, you will be able to see that it is pushing everything to the ECR

Once this is done, you can go to your AWS ECR console to verify that your image has been pushed by finding your image under the image URL.  

![Pushing Everything to the ECR](https://i.ibb.co/3CLYrmH/Pushing-Everything-to-the-ECR.png)

The next step is to deploy and manage the whole thing on the cluster. Hence we will use kubectl to create the deployment

```shell
kubectl create deployment iris-app --image=177300670946.dkr.ecr.us-east-1.amazonaws.com/test-awsecr:v1
```

You will see that your iris-app has been created

-   Expose your application to the internet

```shell
kubectl expose deployment iris-app --type=LoadBalancer --port 5000 --target-port 5000
```

-   To find the URL that needs to be used, type the following code

kubectl get services

Once you get the URL then you need to copy this URL and add ‘:5000’ in your browser and you will get your web application. It will take some time to load the page so you need to wait for a while before getting the web page.

**This is very important to delete the Kubernetes cluster at the end of the process as it costs high if you keep it running.** 

**VIDEO**

**Important note:** 

You need to delete the ECR repository and private hosted zones along with the Kubernetes cluster. It costs too high if you keep it running.

**Deletion of ECR repository:**  
 
![Deletion of ECR Repository](https://i.ibb.co/c8XhgBv/Deletion-of-ECR-Repository.png)

**Deleting Private hosted zone:**

![Deleting Private Hosted Zone](https://i.ibb.co/jJGFCMy/Deleting-Private-Hosted-Zone.png)

Also, as you have provided an auto-scaling option in the cluster creation hence, you need to delete the 2 workers and 1 master node.

**Deleting Autoscaling group:**

![Deleting Autoscaling Group 1](https://i.ibb.co/4gwL9W2/Deleting-Autoscaling-Group-1.png)

![Deleting Autoscaling Group 2](https://i.ibb.co/r7K4LDx/Deleting-Autoscaling-Group-2.png)

**Deleting the load balancer:**

![Deleting the Load Balancer 1](https://i.ibb.co/8s1fB6r/Deleting-the-Load-Balancer-1.png)

![Deleting the Load Balancer 2](https://i.ibb.co/B4gScX0/Deleting-the-Load-Balancer-2.png)

**Once, you have deleted all ELB (Load Balancer) and Autoscaling group, the next task is to terminate EC2, 2 worker nodes and 1 master node.**

**Note: EC2 will not be terminated/stopped as long as Autoscaling group and ELB (Load Balancer) is available in your AWS account. Please delete the auto-scaling group and ELB first and then terminate/stop the EC2 and nodes.**

In this way, you have learnt to deploy ML model on Kubernetes.
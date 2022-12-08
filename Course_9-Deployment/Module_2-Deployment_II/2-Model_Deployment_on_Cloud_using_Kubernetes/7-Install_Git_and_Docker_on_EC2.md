# Install Git and Docker on EC2

In the previous segment, you learnt about Amazon ECS and Amazon ECR. in this segment, you will learn how to install Docker and Git and build a Docker image that can be used to create the container.

Let’s watch the next video to learn how to install Docker and Git on EC2.

**VIDEO**

Now you need to create a repository under ECR. Once the repository is created under ECR, you need to create a Docker image.

But before creating a docker image, you need to install Git on EC2 so that you can import files directly from the public GitHub repository.

a. Install Git:

```shell
sudo yum install git
```

Before importing the public repository from GitHub, let’s understand what we are going to deploy on the Kubernetes cluster.

You are already aware of Iris dataset, where there are majorly four features, which are as follows:

1.  Sepal length
2.  Sepal width
3.  Petal length
4.  Petal width

Based on these four parameters, you can predict the Iris type as 0, 1 and 2 corresponding to Iris Setosa, Iris Versicolor and Iris Virginica, respectively. 

In the video above, Abhay is using the SVM model to predict the Iris type along with the four features. Please note that you are not required to understand SVM to deploy the model.

A public link to a GitHub repository provided below. You can find all the files required for deploying the ML model using Kubernetes cluster.  
 
**[https://github.com/antoinemertz/deploy-ml-flask/blob/master/model.py](https://github.com/antoinemertz/deploy-ml-flask/blob/master/model.py)**

We suggest you **add all of these files to your own Git repository and access the files from your Git repository only.**

You have been provided with all the files in the below folder.

Download [Iris ML Model Files](deploy-ml-flask-master.zip)

-   The next step is to clone the codes into your instance. This is done using the Git clone command.

```shell
git clone https://github.com/antoinemertz/deploy-ml-flask.git
```

-   Go into the particular folder to access the contents from the Git repository

```shell
cd deploy-ml-flask/
```

-   Sometimes, you may face issues with AWS while trying to use ‘Load Balancer’. So, ensure that you add this additional code for attaching the elastic load balancing role.

aws iam create-service-linked-role --aws-service-name "elasticloadbalancing.amazonaws.com"

Now in the next step, you need to install Docker and create the Docker image.

-   Install Docker on EC2

```shell
sudo yum install docker
```

-   Start the Docker service

```shell
sudo service docker restart
```

In the next video, you will create a Docker image.

**VIDEO**

-   Let’s build a Docker image using the following command:

```shell
sudo docker build -t iris-app:v1 .
```

-   Authenticate to container Registry AWS

```shell
sudo $(aws ecr get-login --no-include-email --region us-east-1)
```

-   In the next step, you need to tag the iris-app with the repository URL that we have created using ECR.

```shell
sudo docker tag iris-app:v1 ECR_URL_COPIED_FROM_ECR_REPOSITORY:v1
```

-   Now that you have tagged the Docker image with ECR repository URL now in the next step, the Docker image needs to be pushed into the repository.

```shell
sudo docker push ECR_URL_COPIED_FROM_ECR_REPOSITORY:v1
```

In the next segment, you will learn the final deployment of the ML model using kubectl.
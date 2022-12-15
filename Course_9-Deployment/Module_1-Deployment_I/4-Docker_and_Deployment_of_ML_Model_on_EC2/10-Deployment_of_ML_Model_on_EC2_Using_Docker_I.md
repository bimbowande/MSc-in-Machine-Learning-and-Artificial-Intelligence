# Deployment of ML Model on EC2 Using Docker I

In the previous segments, you built a Docker image and deployed an ML model using Docker in your local system. In this segment, you will learn how to deploy an ML model using EC2 and get a public link to the web application.

Let’s watch the upcoming video to start creating an EC2 instance.

**VIDEO**

Note that you need to add security as given below.

**Type: Custom TCP**  
**Protocol: TCP**  
**Port range: 5000**  
**Source: Custom, 0.0.0.0/0**

Once you have created the EC2 instance, you can install Docker on the EC2 instance.

**VIDEO**

Run the following commands to install Docker on EC2:

```shell
# To install docker on EC2:
sudo amazon-linux-extras install docker

sudo yum install docker

# Start to docker service
sudo service docker start

# Change the user permissions
sudo usermod -a -G docker ec2-user
```

In the next segment, you will learn how to add all the files on EC2 and deploy an ML model on EC2.

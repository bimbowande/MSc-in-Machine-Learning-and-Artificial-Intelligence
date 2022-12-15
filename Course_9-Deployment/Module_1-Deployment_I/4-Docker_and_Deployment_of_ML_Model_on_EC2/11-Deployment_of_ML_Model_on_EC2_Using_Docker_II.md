# Deployment of ML Model on EC2 Using Docker II

In the previous segment, you installed Docker on EC2. Now let’s copy the following files on EC2 using your local system command prompt:

-   requirements.txt
-   model.pkl
-   model.py
-   Dockerfile
-   app.py
-   template/index.html

Let’s watch the upcoming video and copy the files mentioned above on EC2.

**VIDEO**

Note: In the video above, homepricepred.pem was used as the key pair. You need to use your own key pair.

Copy your pem file to the same folder that contains all the files related to ML model building.

Open your cmd.

Also, the pem file should be in the same folder that contains all the files. Now it’s time to run the following commands:

```shell
$ scp -i homepricepred.pem requirement.txt ec2-user@”EC2_PUBLIC_DNS”:/home/ec2-user
$ scp -i homepricepred.pem model.pkl ec2-user@”EC2_PUBLIC_DNS”:/home/ec2-user 
$ scp -i homepricepred.pem model.py ec2-user@”EC2_PUBLIC_DNS”:/home/ec2-user 
$ scp -i homepricepred.pem Dockerfile ec2-user@”EC2_PUBLIC_DNS”:/home/ec2-user 
$ scp -i homepricepred.pem app.py ec2-user@”EC2_PUBLIC_DNS”:/home/ec2-user 
$ scp -i homepricepred.pem template/index.html ec2-user@”EC2_PUBLIC_DNS”:/home/ec2-user
```

Note: If you are using a Windows machine, you can directly transfer the files from your local machine to the EC2 instance using the Winscp software. You can follow the documentation provided in the link below to learn how to transfer files from your local machine to your EC2 or EMR instance.

Download [Transferring Data Local to EC2 or EMR Instance](Docs/Amazon_Web_Services/Transferring_Data_Local_to_EC2_or_EMR_Instance/pdf)

In the next video, you will learn how to build a Docker image and run the application on a public URL.

**VIDEO**

Follow the steps mentioned below to build and run the Docker image on EC2.

```shell
sudo chmod 666 /var/run/docker.sock 

# build docker image 
docker build -t homepriceprediction . 

docker run -p 5000:5000 homepriceprediction
```

After completing all the aforementioned steps, you will get a public link to your web application.
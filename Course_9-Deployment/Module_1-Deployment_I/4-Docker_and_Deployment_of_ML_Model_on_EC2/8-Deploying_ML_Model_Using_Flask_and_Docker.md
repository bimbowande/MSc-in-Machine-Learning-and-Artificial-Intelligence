# Deploying ML Model Using Flask and Docker

In the previous segment, you learned some important Docker CLI commands for viewing and deleting images and containers. In this segment, you will learn how to deploy a housing price prediction linear regression model using Docker.

Before proceeding to the upcoming video, download all the required files from the link provided below.

Download [Docker ML Deployment Files](Docker_ML_Deployment_Files.zip)

For a better understanding of how to deploy the model, perform the steps along with Mithun.

To deploy the ML model using Docker, you require the following three files:

-   app.py
-   Dockerfile
-   requirement.txt

Unzip the downloaded file and open it using Visual Editor. Let’s get started with the segment in the next video.

**VIDEO**

In the video above, you created a Docker file and dockerized the following components. Note that the following code has some modifications to the structured way of implementing Docker in Python3.

```dockerfile
# Create the base image 
FROM python:3.7-slim 

# Change the working directory 
WORKDIR /app/ 

# Install Dependency 
COPY requirements.txt /app/ 
RUN pip install -r ./requirements.txt 

# Copy local folder into the container 
COPY app.py /app/ 
COPY model.pkl /app/ 
COPY templates/index.html /app/templates/index.html 

# Set "python" as the entry point 
ENTRYPOINT ["python"] 

# Set the command as the script name 
CMD ["app.py"] 

#Expose the post 5000. 
EXPOSE 5000
```

Here, one of the important things you need to understand is “WORKDIR.”

You are already aware that the Docker container is an instance of a Docker image.  When you write _“WORKDIR /app/”_ in the Dockerfile, it guides the container to use “app” as the working directory to run all the files available inside that directory. 

So, you need to copy all the required files, such as “requirements.txt,” “model.pkl,” “index.html,” and “app.py” into it. For copying these files, you used the command "COPY.”  

Once you select the WORKDIR as “app,” the container is already in the working directory, and dot (.) (_RUN pip install -r ./requirements.txt_) can be used to run the “requirement.txt” file. 

Suppose you do not define a working directory. In this case, by default, it takes root as the working directory. However, it is recommended to create a new working directory, which is “app” in this case.

Now let's take a look at the “requirements.txt” file. This file is the dependency in this Docker image. The “requirements.txt” file contains all the versions of the tools, as shown in the code below.

```
Flask==1.1.1 
gunicorn==19.9.0 
itsdangerous==1.1.0 
Jinja2==2.10.1 
MarkupSafe==1.1.1 
Werkzeug==0.15.5 
numpy>=1.9.2 
scipy>=0.15.1 
scikit-learn>=0.18 
matplotlib>=1.4.3 
pandas>=0.19
```

In the next video, you will learn how to create a Docker image and deploy an ML model using the Docker image.

**VIDEO**

To build the Docker image, you need to run the following command:  
`docker build -t  homeprice .`

To view the Docker images, you need to run the following command:  
`docker images`

To run the image and get the URL, you need to run the following command:  
`docker run -p  5000:5000 homeprice` 

After performing the above-mentioned steps, you will get the URL (reminder to replace 0.0.0.0 with localhost) to access from your browser.

In the next segment, you will learn some other Docker CLI commands.
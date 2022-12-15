# Hello World: Flask and Docker

In the previous segment, you installed Docker on your local system. The next step is to dockerize a simple Flask application. First, you need to get familiarized with the following two files:

1.  app.py
2.  Dockerfile

You can download both these files using the link below.

Download app.py

Download Dockerfile

**VIDEO**

You learned about the app.py file in the previous sessions. 

  
Note: When you run this app.py file, you will get the following URL: `http://0.0.0.0:5000/` 

  
You need to run the following URL in your browser: `http://localhost:5000/`

Now, let’s understand the code of the Dockerfile one by one.

```dockerfile
# Create the base image
FROM python:3.7-slim
```

This code indicates that you created a base image from python: 3.7-slim. You can use any version of Python. Basically, it informs Docker from which base image you want to create your image. In our example, we are creating an image from the Python image.

```dockerfile
# Install Dependency 
RUN pip install flask==1.1.2
```

This indicates that you have installed Flask version 1.1.2 to gather the dependent libraries, which, in this case, is the Flask library. The RUN command is used for running instructions against the image.

```dockerfile
# Copy local folder into the container 
COPY ./app.py /app/
```

The COPY instruction is used for copying files and directories. Now, you need to copy the app.py file, which is in the local folder, into the container.

```dockerfile
# Change the working directory 
WORKDIR /app/
```

This indicates that you have changed the working directory to app.  
 
```dockerfile
# Set "python" as the entry point 
ENTRYPOINT ["python"]
```

This indicates that you set the entry point as “python.”  
 
```dockerfile
# Set the command as the script name CMD ["app.py"]
```

Finally, this indicates that you have included the CMD command to execute the app.py file. 

In the next video, you will learn how to build the Docker image.

**VIDEO**

Before running the Dockerfile, ensure you press Ctrl + C to stop the previously running Flask application. Here are the steps for deploying Docker images on the container:

-   Run the following command to build a Docker image:

`docker build -t [image_name]:[tag] .`

-   After running the command mentioned above, you will notice that each of the six predefined steps is executed in the CLI. At the end of the execution, you will get an alphanumeric number, which is the Docker ID.
-   You can list out all the Docker images that you have created by entering the following command:

`docker images`

-   You need to deploy the previously created Docker image in a container so that you can start running it. You can use the following command to deploy the Docker image in a container:

`docker run -p 5000:5000 helloflask`

After running the above-mentioned command, you will get the same type of URL that you get from Flask.

With this, you have successfully deployed a Hello_world! Flask application using Docker.
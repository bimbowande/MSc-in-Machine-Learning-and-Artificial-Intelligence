# Summary

With this, you have reached the end of the session on Docker. Note that this is one of the important sessions related to the model deployment and creation of a web application.

Here is a summary of what you learned in this session.

- What Is Docker? 

Docker can be considered as a big container that comes in one shape and size, and fits in a truck used for transporting goods from one place to another. The contents of the boxes do not matter as long as they are packed in containers so that you can transport the goods easily without worrying about the dimensions of the goods.

Docker is similar to that container. It does not matter which system you have deployed the model; once the code is containerized on Docker, the model can be used on all the platforms and will not face issues related to dependency.

When Docker was first introduced, it was compared to virtual machines owing to the similarity in terms of how the two function. Docker can be seen as something that uses less memory and starts faster than a virtual machine.

- The image given below outlines the difference between a virtual machine and Docker. 

![Difference Between a Virtual Machine and Docker](https://i.ibb.co/vLnP4P0/Difference-Between-a-Virtual-Machine-and-Docker.png)

| **Virtual Machine**                        | **Docker**                             |
| ------------------------------------------ | -------------------------------------- |
| Heavyweight                                | Lightweight                            |
| Limited performance                        | Native performance                     |
| Every VM has an OS                         | All containers share the host OS       |
| Hardware-level virtualization              | OS virtualization                      |
| Boots in minutes                           | Boots in milliseconds                  |
| Uses more resource                         | Uses less resource                     |
| Offers complete isolation from the host OS | Shares some resources with the host OS |

- Various Terminologies Related to Docker 

**Docker**: Docker is a containerization platform that packages your application and all of its dependencies in the form of a Docker container to ensure that your application works seamlessly in any environment.

**Container**: Docker Container is a standardized unit that can be created on the fly to deploy a particular application or environment. 

**Docker Image:** Docker image is a read-only template that contains a set of instructions for creating a container that can run on the Docker platform. It provides a way to package applications and preconfigured server environments that can be used for personal purposes or shared publicly with other Docker users. 

A Docker image is an immutable file containing the source code, libraries, dependencies, tools, and other files needed for an application to run.

- Benefits of Using Docker 
1. Ease of the development process
2. Scalability
3. Standardization and productivity
4. Compatibility and maintainability
5. Multi-cloud platform.
- You built the hello docker application using Flask and then deployed an ML model using Docker.
- In the next segment, you ran the following Docker CLI commands:

```shell
# Build a Docker image 
$ docker build -t [image_name]:[tag] . 

# Run a Docker container specifying a name 
$ docker run --name [container_name] [image_name]:[tag]     

$ docker run -p [host:host] [image_name] 

# Fetch the logs of a container 
$ docker logs -f [container_id_or_name] 

# Run a command in a running container 
$ docker exec -it [container_id_or_name] bash 

# Show running containers 
$ docker ps 

# Show all containers 
$ docker ps -a 

# Show Docker images 
$ docker images 

# Stop a Docker container 
$ docker stop [container_id_or_name] 

# Remove a Docker container 
$ docker rm [container_id_or_name] 

# Remove a Docker image 
$ docker rmi [image_id_or_name]
```

In the next segment, you deployed an ML model using Docker on your local machine. Next, you deployed an ML model on EC2 and created a public web application.

With this, you have completed the session on Docker.

# Terminologies of Docker

In this segment, you will learn some basic terminologies associated with Docker. 

In the upcoming video, you will understand the following aspects of Docker:

1.  Docker Container
2.  Docker Image
3.  Benefits of Using Docker

**VIDEO**

Here is a summary of the terms you learned in the video above:

-   **Docker**: Docker is a containerization platform that packages your application and all of its dependencies together in the form of a Docker container to ensure that your application works seamlessly in any environment.
-   **Container**: Docker Container is a standardized unit that can be created on the fly to deploy a particular application or environment.
-   **Docker Image**: Docker Image is a read-only template that contains a set of instructions for creating a container that can run on the Docker platform. It provides a way to package applications and preconfigure server environments that can be used for personal purposes or shared publicly with other Docker users.

A Docker image is an immutable file containing the source code, libraries, dependencies, tools, and other files needed for an application to run.

Since images are just templates, you cannot start or run them. You can only use that template as a base to build a container. Ultimately, a container is a running instance of a Docker image. Once you create a container, it adds a writable layer on top of the immutable image so that you can modify it.

Let’s take a look at images and containers. You are well aware of the Class definition in OOPS programming. The class definition is something that you defined with some variables and methods. You put the type of variables and methods in the class definition, like public or private variables/methods. 
  
You can define the class object from the class definition that you defined earlier. This class object can be called the instance of the class definition. 
  
An image and a container work in the same way. The instance of a Docker image is called a container. Suppose there is a Docker image containing the set of rules in the form of layers described by you. If you run this particular image, you have a running instance of this image, which is called a container of this image. You can have multiple running containers of the same image. In other words, Docker images can be interpreted as a snapshot of the container.
  
You can refer to the links provided at the end of the segment in the Additional Readings section to read more about Docker Container and Docker Image.

Here are some of the benefits of using Docker:

1.  Ease of the development process
2.  Scalability
3.  Standardization and productivity
4.  Compatibility and maintainability
5.  Multi-cloud platform

In the next segment, you will learn how to install Docker.

**Additional Readings**

[Docker images and containers - I](https://searchitoperations.techtarget.com/definition/Docker-image)

[Docker images and containers - II](https://jfrog.com/knowledge-base/a-beginners-guide-to-understanding-and-building-docker-images/#:~:text=A%20Docker%20image%20is%20a,publicly%20with%20other%20Docker%20users.)

[Docker images and containers - III](https://phoenixnap.com/kb/docker-image-vs-container)

[Benefits of Docker - I](https://dzone.com/articles/top-10-benefits-of-using-docker)

[Benefits of Docker - II](https://www.microfocus.com/documentation/enterprise-developer/ed40/ES-WIN/GUID-F5BDACC7-6F0E-4EBB-9F62-E0046D8CCF1B.html)

#### Docker

Qn: Which of the following statements is true?

- A Docker image is a writable template.

- A Docker image is an immutable file containing the source code, libraries, dependencies, tools, and other files needed for an application to run.

- You need to have the same environment that you are using to create an application to run Docker in another system.

Ans: B.

Qn: Write down five major benefits of using Docker?

Ans: *Here are some of the benefits of using Docker:*

- *Caching a cluster of containers*

- *Flexible resource sharing*

- *Scalability - many containers can be placed in a single host*

- *Running your service on hardware that is much cheaper than standard servers*

- *Fast deployment, ease of creating new instances, and faster migrations.*

- *Ease of moving and maintaining your applications*

- *Better security, less access needed to work with the code running inside containers, and fewer software dependencies*

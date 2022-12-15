# Docker CLI Commands - I

In the previous segment, you learned how to deploy a simple Flask application using Docker. In this segment, you will learn some important Docker CLI commands.

Let’s consider the Hello_world! example and run some of these commands.

**VIDEO**

The following commands were used in the video above:

```shell
# Build a Docker image
$ docker build -t [image_name]:[tag] .

# Run a Docker container specifying a name
$ docker run --name [container_name] [image_name]:[tag]
     $ docker run -p [host:host] [image_name]

# Fetch the logs of a container
$ docker logs -f [container_id_or_name]

# Run a command in a running container
$ docker exec -it [container_id_or_name] bash

# Show running containers
$ docker ps

# Show all containers
$ docker ps -a

# Show Docker images
$ docker images

# Stop a Docker container
$ docker stop [container_id_or_name]

# Remove a Docker container
$ docker rm [container_id_or_name]

# Remove a Docker image
$ docker rmi [image_id_or_name]
```

In the next segment, you will learn how to deploy the house price prediction ML model using Docker.
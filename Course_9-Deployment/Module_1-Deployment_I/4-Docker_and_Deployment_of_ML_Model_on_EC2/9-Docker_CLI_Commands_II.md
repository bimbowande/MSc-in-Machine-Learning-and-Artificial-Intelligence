# Docker CLI Commands - II

In the previous segment, you learned the most commonly used CLI commands. In this segment, you will learn some other CLI commands.

For a better understanding of the commands, run them as shown in the upcoming video.

**VIDEO**

The following CLI commands were used in the video above:

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

In the next segment, you will learn to deploy the ML model on EC2 using Docker.

#### Docker Commands

Qn: What is the command to list all the running containers?

- docker ps

- docker run

- docker start 

- docker pull

Ans: A. *This is the correct command to list all the containers.*

Qn: How to access a running container?

- `docker ps -it <container_id> bash `

- `docker run  -it <container_id> bash `

- `docker start  -it <container_id> bash `

- `docker exec  -it <container_id> bash`

Ans: D.

Qn: How to delete an image from a local storage system?

- `docker rm <image_id>`

- `docker rmi <image_id>`

- `docker delete <image_id>`

- `docker exec  <image_id>`

Ans: B.

Qn: How to build a Dockerfile?

- `docker rm  <Dockerfile-path>`

- `docker delete  <Dockerfile-path>`

- `docker build <Dockerfile-path>`

- `docker exec   <Dockerfile-path>`

Ans: C.

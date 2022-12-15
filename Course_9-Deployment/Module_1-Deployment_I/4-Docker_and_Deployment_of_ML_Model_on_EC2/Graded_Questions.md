# Graded Questions

#### Graded questions

Qn: Which of the following are not the features of Docker? (Note: More than one option may be correct.)

- All containers have their own OS.

- Docker uses less RAM than VMs.

- Docker supports hardware-level virtualization.

- Docker boots faster than VMs.

Ans: A & C. *All the containers share the host OS. Docker supports OS-level virtualization.*

Qn: How do you delete an image from a local storage system?

- `docker exec  <image_id>`

- `docker delete <image_id>`

- `docker rm <image_id>`

- `docker rmi <image_id>`

Ans: D.

Qn: Which of the following statements are true? (Note: More than one option may be correct.)

- Sharing the host operating system makes containers very heavy, because of which they take a long time to boot up.

- Docker containers are best suited for running multiple applications over a single operating system.

- A Docker image is a read-only template containing a set of instructions for creating a container that can run on the Docker platform.

- A Docker image is a mutable file.

Ans: B & C.

Qn: Which of the following commands is used for creating a Docker image?

- `build docker image -t [image_name] .`

- `doc build -t [image_name] .`

- `build -t [image_name] .`

- `docker build -t [image_name] .`

Ans: D.
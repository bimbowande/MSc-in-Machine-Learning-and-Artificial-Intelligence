# What is Docker? - Part II

In this segment, you will understand the difference between a virtual machine and Docker. Let’s hear from Abhay as he explains this in detail.

**VIDEO**

Now that you know what the architecture of a virtual machine looks like, let's watch the next video to understand the architecture of Docker.

**VIDEO**

The image depicts the difference between a virtual machine and Docker.

![Difference Between a Virtual Machine and Docker](https://i.ibb.co/vLnP4P0/Difference-Between-a-Virtual-Machine-and-Docker.png)

As you can see in the image above, each virtual machine has its own guest operating system, which makes it heavy. On the other hand, Docker containers share the host operating system; hence, they are lightweight.

As the containers share a single host operating system, they are very light and boot up in just a few seconds. Hence, the overhead cost of managing the container system is lower than that of VMs.

Docker containers are best suited for running multiple applications over a single operating system. However, if you need to run applications or servers on different operating systems, then you will require virtual machines.

Let’s take another example to understand the difference between Docker and VMs.

Suppose you have a host system that has 20 GB RAM. You allocate 8 GB, 7 GB, and 5 GB of RAM to each of the three VMs.

Now, VM1, VM2, and VM2 only require 6 GB, 3 GB, and 4 GB, respectively, to run their applications. So, a total of 7 GB RAM gets wasted, which could be used for creating a new VM.

However, in the case of Docker, the CPU will allocate the exact amount of memory required for the container. The remaining 7 GB of memory may be used to create a new container.

The table below outlines the differences between VMs and Docker.

| **Virtual Machine**                        | **Docker**                             |
| ------------------------------------------ | -------------------------------------- |
| Heavyweight                                | Lightweight                            |
| Limited performance                        | Native performance                     |
| Every VM has an OS                         | All containers share the host OS       |
| Hardware-level virtualization              | OS virtualization                      |
| Boots in minutes                           | Boots in milliseconds                  |
| Uses more resource                         | Uses less resource                     |
| Offers complete isolation from the host OS | Shares some resources with the host OS |

In the next segment, you will learn some basic terminologies associated with Docker.

#### Docker and VM

Qn: Which of the following are the features of a virtual machine? (Note: More than one option may be correct.)

- VMs uses hardware-level virtualization.

- VMs use more resources than Docker.

- VMs use OS-level virtualization.  
 
Ans: A & B.

#### VM and Docker

Qn: Write five differences between VMs and Docker?

Ans: *VMs have the host OS and guest OS inside each VM. A guest OS can be any OS, like Linux or Windows, irrespective of the host OS. In contrast, Docker containers host on a single physical server with a host OS, which shares among them. Sharing the host OS between containers makes them light and increases the boot time.*

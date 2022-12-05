# What is Docker? - Part I

In the previous session, you learned how to deploy models using Flask and Heroku. In this session, you will learn how to deploy models in Docker using Flask.

First, you need to understand what Docker is and why it is used.

**VIDEO**

Suppose you have deployed a model on your computer, and it works perfectly fine. When you present it to your boss, he decides to run it on his computer. However, he does not have the same version of the Linux operating system as you, so he faces some issues with his system. This is where Docker comes into the picture.

In the previous video, you got an intuitive sense of what Docker would do. Let’s understand this from a technical perspective in the following video. 

**VIDEO**

Consider Docker as a big container that comes in one shape and size and fits in the truck used for transporting goods from one place to another. The contents of the boxes in the truck do not matter as long as they are packed in containers so that you can transport the goods easily without worrying about the dimensions of the goods. According to this analogy, Docker is the container, and the truck can be considered as the machine on which the contents of Docker will run and hence not face any dependency issues.

  
When Docker was first introduced, it was compared to virtual machines owing to the similarity in terms of how the two function. However, Docker uses less memory and starts faster than a virtual machine.

  
In the next segment, you will see a comparison between running a server on Docker and running it on a virtual machine.
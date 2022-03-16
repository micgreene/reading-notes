# Django REST Framework & Docker

## Linux Containers

+ Docker is really just Linux containers which are a type of virtualization.
+ Virtualization has its roots at the beginning of computer science when large, expensive mainframe computers were the norm. How could multiple programmers use the same single machine? The answer was virtualization and specifically virtual machines which are complete copies of a computer system from the operating system on up.
+ If you rent space on a cloud provider like AWS they are typically not providing you with a dedicated piece of hardware. Instead you are probably sharing a physical server with hundreds or even thousands of other clients.
+ What’s the downside to a virtual machine? Size and speed. A typical guest operating system can easily take up 700MB of size. So if one physical server supports three virtual machines, that’s at least 2.1GB of disk space taken up along with separate needs for CPU and memory resources. 

## Containers vs Virtual Environments

+ Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

## Hello, World

+ To confirm Docker installed correctly we can run our first command docker run hello-world. This will download an official image and then run the container.

## Images and Containers

+ Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.
+ When we ran hello-world we used an official Docker image. We did not have to create the image ourself. But typically we will create custom images and we do so using a Dockerfile. We also will use docker-compose.yml files to run the containers.
+ A baking analogy we can use here is as follows:
  + A Dockerfile is the recipe for a cake
  + An image is a snapshot of the recipe at a given time
  + A docker-compose.yml says how to make the cake
  + And the container is the actual, baked cake

## Conclusion

+ The important takeaways from this tutorial are this:
  + Docker is a way to run Linux containers
  + Containers are a lightweight alternative to Virtual Machines
  + Dockerfile is a list of instructions for creating an image
  + Images are made up of one or more layers
  + Containers are a running instance of an image
  + docker-compose.yml controls how to run the container
  + Containers are stateless and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases (which we didn’t cover here).

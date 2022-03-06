# Docker
## 1. Docker:(gives a portable container) Docker is a tool which is used to automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments.

Note: The container is actually a software package that consists of all the dependencies required to run the application. So, miltiple containers can run on the same computer.   

### Install Docker
```
# to install follow: https://www.youtube.com/watch?v=aMKUuaga85A
# chaeck docker version
$ docker --version
# lets create and run a hello world cimage, to check docker is working correctly
$ sudo docker run hello-world
# here is 'hello from docker!' comes out then everything is fine
# see the current docker images
$ sudo docker images
# see all the containers->
$ sudo docker ps -a
# see the container that currently running
$ sudo docker ps

## Now we want to work with docker without 'sudo' word
# so, search(on google) for 'stop using sudo with docker' 
# or goto: https://docs.docker.com/engine/install/linux-postinstall/
# and follow the instruction

# now we can use docker command, without 'sudo'
# see all the containers: 
$ docker ps -a
# copy the name of the container and use remove command to delete the container
$ docker rm container_name
# here, rm = remove

# we can see image ID by :
$ docker images 
# same way we can delete the images
$ docker rmi image_id
# here rmi = remove image
```
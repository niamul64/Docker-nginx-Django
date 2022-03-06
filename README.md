# Docker
## 1. Docker:(gives a portable container) Docker is a tool which is used to automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments.

```
Create: docker file (contains set of instructions) ---> use this file --> docker image 

'Dockerfile' have no extensions
```

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
<hr>

# docker file: (see video 1.mp4 in this reposetory and in this branch)


### 1st line: the image that we are going to inherit from. (means, we can built a docker image --> ontop of other image)
#### we can use a pre built image(from: hub.docker.com) and customize that:
#### goto hub.docker.com , search python, choose first one from search list. from there choose a version of alpine. 
### 2nd line: maintainer line(optional): can be used own or company name
### 3rd line: environment variable python un buffered 
### 4th line: from where it copy the dependencies 
#### copy from to
### 5th line: pip install the packages from requirements.txt
### 6th line: create a directory to store the project 
### 7th line: change directory to app
### 8th line: copy to local machine app folder to docker image app folder
### 9th line: create user --> which will run the application
### 10th line: switch to that user
#### example:
```
FROM python:3.7-alpine
MAINTAINER London App Developer Ltd.

ENV PYTHONUNBUFFERED 1

# Install dependencies --> this is a comment comment
COPY ./requirements.txt /requirements.txt
RUN pip install -r /requirements.txt

# Setup directory structure
RUN mkdir /app  # create a directory on our docker image named 'app'
WORKDIR /app    # change directory to created 'app'
COPY ./app/ /app

RUN adduser -D user
USER user
```


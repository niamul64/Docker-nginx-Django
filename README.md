# 1.Docker  2.docker compose 3.Create django project using docker configuration
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
<br><br>

#  Now, to create docker image
### steps:
### 1. create a empty file called app. as mentioned in dockaer file.(this app could be any other name)
### 2. command: (directed to the docker file folder)
```
$ docker build .
```
<br><br>

## 2. docker compose: A tool that allows us to run our docker image easily from our project location. so it allows us to run our docker image easily from our project location. Docker Compose is a tool that was developed to help define and share multi-container applications. With Compose, we can create a YAML file to define the services and with a single command, can spin everything up or tear it all down.

### First of--> create a file 'docker-compose.yml' at the root of our project

```
# docker-compose.yml
version: '3' #docker  version

services:
  app: ## main of our service
    build:
      context: . ## . means corrent directory
    ports:+
      - "8000:8000"
    volumes: # keep updating the changing
      - ./app:/app
    command: > ## command to run the application in a docker container
      sh -c "python manage.py runserver 0.0.0.0:8000"
```
### will build our image using using docker compose..
### Now, run command ->> docker-compose build.

<br><br>

# 3.Now, to create django project usig docker: (Check video 2 in this reposetory and in this branch)
example commands: 
```
command docker-compose run app sh -c "django-admin.py startproject app ." # . means create app in current location
```
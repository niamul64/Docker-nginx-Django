# Docker-nginx-Django

## 1. Docker:(gives a portable container) Docker is a tool which is used to automate the deployment of applications in lightweight containers so that applications can work efficiently in different environments.

Note: The container is actually a software package that consists of all the dependencies required to run the application. So, miltiple containers can run on the same computer.   

## 2. Nginx:Webserver that provides Improve the Performance, Reliability, and Security of Your Applications.
```
NGINX is,
      1. Webserver
            Serves web content
      2. Proxy
            Load balancing
            Backend ROuting
            Caching
```

## 3. Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design


## technologies that we will use-->
```
Docker (Create microservice Architecture)
Django (To run web application)
Nginx (Load balancing)
Redis (cache)
Gunicorn (WSGI server )
```

## install anaconda(for python virtual environment) : can follow a video to install the anaconda(video is in this reposetory named 'ananconda install')
## Use Pycharm
## install and configure docker(to containerize our web App)

## Now, Start working:

### Install anaconda and test
```
# Create virtual python environmnet using ananconda:(environment name = test_env) (if any problem, then watch video in this reposetory, named as 'anaconda install')
$ conda create -n test_env python=3.8
# Activate the newly created vertual environment
$ source activate test_env
# now install django in that environment 
$ pip install django
# now, run python sheel, and import django and check the version of django
$ python
      >>> import django
      >>> django.__version__
      '4.0'
      >>> quit()
# BUT we will use 3.2
# Now to get out from the Our test_env
$ conda deactivate
```
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
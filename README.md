# Docker-nginx-Django

## 1 Docker: 
	### see the branche in this repesetory: docker 


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

</br></br> </hr>

# Now, we will build a project using: technologies that we will use-->

```
Docker (Create microservice Architecture)
Django (To run web application)
Nginx (Load balancing)
Redis (cache)
Gunicorn (WSGI server )
```
## Django is a high-level Python web framework that encourages rapid development and clean, pragmatic design

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

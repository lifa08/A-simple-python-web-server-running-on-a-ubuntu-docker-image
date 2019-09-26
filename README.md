# A-simple-python-web-server-running-on-a-ubuntu-docker-image

This application runs a simple python web server on a ubuntu docker image. The web server uses redis to store the number of visits. In this case, the redis server has to be run somewhere. There are two methods to accomplish this. 

## First methon - run redis server on the same ubuntu docker image

Implemented in **redis_in_ubuntu**

However, a Docker container cannot run two commands at the same time, so after runing the web server, we have to open another terminal to execute the same docker and launch redis server on it. More seriously, the ubuntu image has to run with root user in order to start the redis-server which might have security issues. 

## Second method - use redis docker image and link to it in the web server application

Implemented in **redis_in_container**

This method is simple and safe.


*Note:* in the first method inside file app.py Redis(host="**localhost**"...., while in the second method, Redis(host="**redis**"

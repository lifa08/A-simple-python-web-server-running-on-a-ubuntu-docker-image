# use redis docker image and link to it in the web server application.

## download redis docker image and run it

`$ docker pull redis`
`$ sudo docker run --name my-redis-container -d redis`

## Launch python web application container and link it to above running redis container

`$ docker run --link my-redis-container:redis -p 4000:4000 --rm -it lifa08/python_web_server_redis`

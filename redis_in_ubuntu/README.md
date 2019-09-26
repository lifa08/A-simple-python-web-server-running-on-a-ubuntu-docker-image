# usage
docker build
`$ docker build -t lifa08/python_web_server .`

docker run
# $ docker run -p 4000:4000 -it lifa08/python_web_server


# open a terminal and run $ docker ps to get the container id
# $ docker exec -it container id bash 

# inside the docker image run # redis-server /etc/redis/6379.conf
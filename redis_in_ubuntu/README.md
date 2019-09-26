# Run redis server on the same ubuntu docker image

## Run python web server

* Docker build
`$ docker build -t lifa08/python_web_server .`

* Docker run
`$ docker run -p 4000:4000 -it lifa08/python_web_server`

## Run redis server

* Open a terminal and run `$ docker ps` to get the container id
`$ docker exec -it container id bash` 

* Inside the docker image run `# redis-server /etc/redis/6379.conf`
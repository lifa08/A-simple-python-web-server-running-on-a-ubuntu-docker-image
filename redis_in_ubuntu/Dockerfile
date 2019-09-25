# usage docker build: $ docker build -t lifa08/python_web_server .
# $ docker run -p 4000:4000 -it lifa08/python_web_server
# open a terminal and run $ docker ps to get the container id
# $ docker exec -it container id bash
# inside the docker image run # redis-server /etc/redis/6379.conf

# Problems: first, it has to run with root user in order to run redis-server which
# might have security issues, second, too complicated, have to open two terminals

FROM ubuntu:latest
RUN apt-get update

RUN apt-get install -y python-pip
RUN apt-get install -y redis-server
COPY 6379.conf /etc/redis/

# Do rest as non-root user
RUN adduser ubuntu
# USER ubuntu

# Create project folder
RUN mkdir /home/ubuntu/Projects
RUN mkdir /home/ubuntu/Projects/unbuntu_webserver

# Create docker volume to project files
VOLUME ["/home/ubuntu/Projects/unbuntu_webserver"]
WORKDIR /home/ubuntu/Projects/unbuntu_webserver

# Install required python libraries
COPY requirements.txt /home/ubuntu/Projects/unbuntu_webserver
RUN pip install --trusted-host pypi.python.org -r requirements.txt

# Run python web server
COPY app.py /home/ubuntu/Projects/unbuntu_webserver
EXPOSE 4000
ENV NAME World

CMD ["python", "/home/ubuntu/Projects/unbuntu_webserver/app.py"]

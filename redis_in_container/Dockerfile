FROM ubuntu:latest
RUN apt-get update

RUN apt-get install -y python-pip

# Do rest as non-root user
RUN adduser ubuntu
USER ubuntu

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

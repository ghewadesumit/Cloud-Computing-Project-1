# Cloud-Computing-Project-1
Docker Cloud uses Docker Hub as its native registry for storing both public and private repositories. 
Once the images is pushed to Docker Hub, they are available in Docker Cloud.
The Objective of the Docker application is to run  java web application via docker image. Docker is a tool designed to make easier to create, deploy, and run applications by using containers.

Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and ship it all out as one package.
Docker provides a stand-alone Linux environment where you can install your libraries and run your application within an isolated environment. As we have installed application in AWS already, we should be able to install it into Docker.

Here the web application takes an input date and then gives weather forecast TMIN, TMAX for at least 5 days and these records are then populated in a table.

## Getting Started
1. Create Dynamic User Interface web application to consume REST API service. 
2. The Dynamic UI java web application includes HTML, CSS, Angular JS and executed it over apache tomcat 8.5.39 server on local machine.
3. Then created an AWS linux EC2 instance. Connected to the instance and copied REST API application war file in the home directory of linux instance.Installed apache-tomcat-8.5.39 on the linux instance and finally placed my application war file in the webapps folder of apache tomcat.
4. Next, in a web browser, typed the public DNS address (or the public IP address) of my instance with appending port 8080 and application-name to run my application on amazon linux instance EC2.
5. Now, After running the application on tomcat server and testing it. After confirmation of it successfully running on tomcat. Shutted the tomcat server to open port 8080 to docker.

## Docker steps:
1. install docker using sudo yum install -y docker
2. start the docker service using sudo service docker start
3. create a Dockerfile inside /usr/java/apache-tomcat/webapps/
4. Write the following commands in that Pull base image From tomcat8:-jre8 Maintainer MAINTAINER "Sumit Ghewade <ghewadsa@mail.uc.edu"> Copy to images tomcat path ADD Rest_proj.war /usr/local/tomcat/webapps/
5. Build docker image using docker build -t webserver .
6. run docker containeer using docker build -it --rm -p 8080:8080 --name Rest_proj webserver
7. use this link http://ec2-54-186-40-227.us-west-2.compute.amazonaws.com:8080/Rest_proj/ to access project.
8. we use "docker images" command to check all the docker image files.
9. we use "docker ps" to check all the running containers. 10.use "docker commit 8f6d386f397d ghewadesumit/8f6d386f397d" command to commit our image file to our docker hub account.
10. docker login --username --password to log in into docker.hub account.
11. we the use "docker push ghewadesumit/8f6d386f397d" command to push our docker file to docker hub.
12. to pull the docker image file on any device, use command "docker pull ghewadesumit/8f6d386f397d:latest".

Run the docker image
You can run the image by using command "docker run -p 8080:8080 ghewadesumit/8f6d386f397d"

## Pre-requisites
Internet connection 
Prior Knowledge of AWS and Docker.

## Reference

https://www.youtube.com/watch?v=_d-c9uGcUrU

https://github.uc.edu/tatavag/CloudComputing2019/wiki/Docker---Hands-on
 
http://codeomitted.com/deploy-war-file-to-docker-image/

## Author

* **Sumit Ghewade** - *Initial work* - [ghewadesumit](https://github.com/ghewadesumit)

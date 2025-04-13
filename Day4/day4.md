# Docker
create instance in aws open that in putty with changes in ssh and connection(make it 60)
in putty:
* sudo su
* yum install docker -y
* docker --verion
* service docker status
* service docker start
API gateway
* portability
* what is dev environment? env is like a server where we run our application/to check the minimal functionality in the env.

* testing environment - where the software tesing team performs the functional test cases, non functional test cases and performs performance testing, load testing,

* user acceptant test - befor releasing a product into the market we hav to show prototype of the product to the customers

* production env - where we can actual deploy the application so that customers can access the application

* what is container? it is a server or virtual machine where actual weare goin to run the application

* dockerfile is a text document, it contains set of instruction, how to run a application in a container

* DOCKER FILE INSTRUCTION:

1.FROM INSTRUCTION
* will define base image or parent image of the application
* every docker file must start with FROM instruction

2.COPY:
* to copy a file or directory from local machine into a docker image.

3.ADD
* it is same as the COPY instruction
* to download package from internet to docker image.
* add<>URL<>destination_folder

4. RUN

* it is going to help in downloading the dependency packages or install packages in the container or install dependencies in the container

5.DOCKERIGNORE

* if u want to remove unnceessary packages or files while building a docker image we r going to use .dockerignore
6.CMD COMMAND

* defines which code or which artifact that we hav to run in the container.
7.ENTRYPOINT

* defines entry of the application , cmd allows runtime arguments , while entrypoint will not allow the runtime arguments.
8.EXPOSE

* defines on which port number u want to access the application
ENV

defines environment variable of the application
9.WORKDIRECTORY

* defines keep the files inside the container
10.USER

* if u want to create user accounts then we will use user instructions.
docker image is template, it contains what u need to run the application i.e it contains source code, dependencies,confg file, lib files, which platform u want to run ur application "Build once, Run anywhere"

docker hub is registry/lib where we can store all the docker images

developer---> dockerfile---->docker image---> deploy--->run the application--->testing

# COMMANDS:
* sudo su

* yum install docker -y

* docker --verion

* service docker status

* service docker start

* service docker status

* clear

* docker create ubuntu /bin/bash (creates docker image)

* service docker start

* docker ps -a (it shows all the containers irrespective of the state)

* docker start <copy code from docker ps -a > (container id i.e 4a2f8e97582c)

* docker ps (it will show the running containers)

* docker ps -a

* docker create -it --name webserver amazonlinux /bin/bash

* docker ps -a

* docker start webserver

* docker ps (will show the running containers)

* docker exec -it webserver /bin/bash(to go inside the container)

* ls

* exit(to come out of the container)

* docker run -it --name sample ubuntu /bin/bash

* ctrl+p+q (to come out of the container)

* docker ps

* docker run -td --name web-app -p 3002:3000 murulisocial123/cart-page-test:1.0

* docker ps

what is demon containers or detach mode

every microservice works in diff port number

host port number ---> is a user choice , we can give any port number of any choice , this port humber shows how to access application from the server port number ---

dimple repository-fork-then master branch code copy then clone in powershell using-git clone -b master https://github.com/Sinchan08/Dimple-CapsuleProject.git then in vs code-open folder-c drive-users-dell folder-dimple project open

As a devops engineer we need to collect environment variables,port numbers,database endpoints

steps while writing docker file: 1)identify the base image of the application 2)create a work directory 3)copy the dependencies in docker image 4)install the dependencies 5)copy whole source code from local machine into docker image 6)define the expose port number 7)mention which port we have to run in container

server(putty):
yum install git -y 1)git clone -b master https://github.com/Sam/Dimple-CapsuleProject.git 2) ls 3)cd Dimple-CapsuleProject 4)docker build -t web-app-nodejs:1.0 . 5)docker images 6) docker inspect web-app-nodejs:1.0- inorder to know which images are there 7) docker run -td --name node-app -p 3015:3015 web-app-nodejs:1.0 8)then copy the public url and paste in new tab-http://51.44.97.180:3015/ 9) docker run -td --name node-app -p 3015:3015 web-app-nodejs:1.0

1)create a website using chatgpt and write a docker file for that application and deploy in enginx server 2)identify the problems with containers

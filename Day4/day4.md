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

defines which code or which artifact that we hav to run in the container.
ENTRYPOINT

defines entry of the application , cmd allows runtime arguments , while entrypoint will not allow the runtime arguments.
EXPOSE

defines on which port number u want to access the application
ENV

defines environment variable of the application
WORKDIRECTORY

defines keep the files inside the container
USER

if u want to create user accounts then we will use user instructions.
docker image is template, it contains what u need to run the application i.e it contains source code, dependencies,confg file, lib files, which platform u want to run ur application "Build once, Run anywhere"

docker hub is registry/lib where we can store all the docker images

developer---> dockerfile---->docker image---> deploy--->run the application--->testing

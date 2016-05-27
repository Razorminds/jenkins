## Jenkins with DockerOutsideDocker support
Jenkins  Docker images with ability to build docker images. Based on official [jenkins-alpine](https://hub.docker.com/_/jenkins/) image
![jenkins logo](http://i.imgur.com/KC6TAD3.png)
* [Prerequisites](#Prerequisites)
* [How to build locally](#How-to-build-locally)
* [How to run](#How-to-run)
* [Usage](#Usage)

##Prerequisites
Solution is tested tested on the following system
Docker Client:
 Version:      1.11.1<br>
 API version:  1.23<br>
 Go version:   go1.5.4<br>
 Git commit:   5604cbe<br>
 Built:        Tue Apr 26 23:30:23 2016<br>
 OS/Arch:      linux/amd64<br>

Server:
 Version:      1.11.1
 API version:  1.23
 Go version:   go1.5.4
 Git commit:   5604cbe
 Built:        Tue Apr 26 23:30:23 2016
 OS/Arch:      linux/amd64

##How to build locally

    docker build .
    docker run -it  -v /var/run/docker.sock:/var/run/docker.sock *your image id*

##How to run
Following command pull latest image from dockeHub, run it, and mount sockets from
host docker engine into the container. This way container has full access to host docker engine
thought root user and partial  (no docker ps etc.) from jenkins user.

    docker run -d -v /var/run/docker.sock:/var/run/docker.sock glyashen/jenkins:latest

To persist settings on host:

    docker run -d  -v /var/run/docker.sock:/var/run/docker.sock
    -v /home/jenkins_config:/var/jenkins_home jenkins glyashen/jenkins:latest
    glyashen/jenkins:latest

##Usage
The bottom command run docker container with jenkins and
installed docker client. To run docker from jenkins user:
sudo docker run hello-world.
docker ps and some other commands are available only from
root  account




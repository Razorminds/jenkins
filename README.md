# Jenkins with [DockerOutsideDocker support]
Jenkins  Docker images with ability to build docker images. Based on official <a href="https://hub.docker.com/_/jenkins/"> jenkins-alpine</a>
 image
![jenkins logo](https://raw.githubusercontent.com/docker-library/docs/3ab4dafb41dd0e959ff9322b3c50af2519af6d85/jenkins/logo.png)
#Prerequisites
Solution is tested tested on the following system
Docker Client:<br>
 Version:      1.11.1<br>
 API version:  1.23<br>
 Go version:   go1.5.4<br>
 Git commit:   5604cbe<br>
 Built:        Tue Apr 26 23:30:23 2016<br>
 OS/Arch:      linux/amd64<br>

Server:<br>
 Version:      1.11.1<br>
 API version:  1.23<br>
 Go version:   go1.5.4<br>
 Git commit:   5604cbe<br>
 Built:        Tue Apr 26 23:30:23 2016<br>
 OS/Arch:      linux/amd64<br>

#How to build locally
docker build .
docker run -it \
 -v /var/run/docker.sock:/var/run/docker.sock *your image id*

#How to run
Following command pull latest image from dockeHub, run it, and mount sockets from
host docker engine into the container. This way container has full access to host docker engine
thought root user and partial  (no docker ps etc.) from jenkins user.

docker run -d -v /var/run/docker.sock:/var/run/docker.sock glyashen/jenkins:latest

To persist settings on host:

docker run -d  -v /var/run/docker.sock:/var/run/docker.sock
-v /home/jenkins_config:/var/jenkins_home jenkins glyashen/jenkins:latest
glyashen/jenkins:latest

#Usage
the bottom command run docker container with jenkins and
installed docker client. To run docker from jenkins user:
sudo docker run hello-world.

docker ps and some other commands are available only from
root  account




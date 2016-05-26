# jenkins
Jenkins Docker images with ability to build docker images
#How to run
docker build .
docker run -it \
 -v /var/run/docker.sock:/var/run/docker.sock *your image id*

#usage
the bottom command run docker container with jenkins and
installed docker client. To run docker from jenkins user:
sudo docker run hello-world
docker ps and some other commands are available only from
root  account




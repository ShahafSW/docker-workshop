###################################################################
###################################################################
			DOCKER BASICS
###################################################################
###################################################################


#For this workshop we need DockerCE installed on your laptop/server
#So lets run the following command to verify that we have docker installed
docker --version

#Now, lets pull an image of nginx:alpine 
docker pull nginx:alpine

#Let's verify this image is pulled to our local machine
docker images

#Now - let's create a container from this image 
docker run -it nginx:alpine

#Lets view the container
docker ps -a

#Remove the container
docker rm <Container ID>

#Make sure it got deleted
docker ps -a

#Removing an image
docker rmi <Image ID>

#Verify it got deleted
docker images

#Let's create some more interesting containers
#Notice we run it with -d so the docker will be in detach mode and not attached to our current screen.
#Also we user -p option in order to map port 80 from the container to our host.
docker run -d -p 80:80 --name=nginx nginx:alpine

#Now we can browse into the server on port 80
http://<IP>

#If we want to stop a container
docker container stop <Container ID>

#And to start it 
docker container start <Container ID>

#Now we want to execute a command inside the container
docker exec -it <Container ID> ls -l /

#With "docker exec" we can even run a shell inside the container
docker exec -it nginx sh

#Lets remove this container by
docker stop <Container ID>
docker rm <Container ID>

#Other flags of docker run are -v for mounting folder from the host to the container -e for setting environtment variable
docker run -it -e TEST=myname -v ~/docker-workshop/src:/mnt ngnix:alpine

#In order to do some checks we may would like to copy files from/to our container, we will use the command docker cp for example
docker cp src/index.html <Container_ID>:/usr/share/nginx/html 
#We changed the default index file on our nginx container and now when we will check http://<Server IP> we will see the new page













###################################################################
###################################################################
			GREAT JOB!
###################################################################
###################################################################

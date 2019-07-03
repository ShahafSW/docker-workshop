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

#Let's create some more interesting containers
docker run -d -p 80:80 --name=nginx nginx:alpine
#Notice we ran it with -d so the docker will be in detach mode and not attached to our current screen.

In order to check the status of the docker container we can execute
docker ps -a

#Also we user -p option in order to map port 80 from the container to our host.
#Now we can browse into the server on port 80: http://<IP>

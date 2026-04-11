## Build Your Docker Cheat Sheet

## Container commands 
- docker run <container_id>:  runs the container from image.
- dokcer ps: displays all running containers.
- docker stop <container_id>: stops the running the container.
- docker rm <container_id>: removes the stopped container.
- docker exec -it <container_id> bash: used to run a new command inside an already running container.
- docker logs <container_id>: shows the logs of that container

## Image commands
-  docker build <docker_file_path>: converts dockerfile into image.
-  docker pull <username/image>: downloads image from dockerhub.
-  docker push <username/image>: used to upload image to dockerhub.
-  docker tag <old_tag> <new_tag>: changes the name of image.
-  docker image ls: lists all images.
-  docker rmi <image_id>: removes image.

## Volume commands
- docker volume create <volume_name>: used to create volume.
- docker volume ls : lists all the volumes.
- docker inspect <volume_name>: used to know the informations about volume.
- docker volume rm <volume_name>: removes the volume.

## Network commands
- docker network create <network_name>: creates a named network
- docker network ls: lists all networks
- docker network inspect <network_name>: used to know the informations about network.
- docker network connect <network_name> <container_name_or_id> : used to add network to running containers.
- docker network disconnect <network_name> <container_name_or_id> : used to removes network from running containers.

## Compose commands
- docker compose up: runs the docker-compose.yml file.
- docker compose down: stops and removes containers from docker-compose.yml file.
- docker compose ps: lists the containers associated with the current Compose project and tells you their current state.
- docker compose logs:  displays and aggregates the stdout/stderr output from all services in your current Compose project.
- docker compose up --build: builds the image and runs container from image from docker-compose.yml file.

## Cleanup commands 
- docker system prune: removes all unused Docker data (stopped containers, unused networks, and dangling images) to reclaim disk space.
- docker system df: checks how much disk space Docker is using.

## Dockerfile instructions
- FROM: used to take base image for application.
- RUN: used to execute command for downloading necessary dependencies and libraries for application. 
- COPY: copies the data from local to image then to container.
- WORKDIR: creates working directory in image.
- EXPOSE: used to indicating ports for application to run.
- CMD: used to execute final command when docker file is ready to build image . Its commands are fixed .
- ENTRYPOINT: same as CMD but in this we can append commands to it .


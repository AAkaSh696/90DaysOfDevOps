## Day 30 – Docker Images & Container Lifecycle

## Task 1: Docker Images
1. Pull the nginx, ubuntu, and alpine images from Docker Hub
  - docker pull nginx
  - docker pull ubuntu
  - docker pull alpine
2. List all images on your machine — note the sizes
   - docker ps -a   
3. Compare ubuntu vs alpine — why is one much smaller?
   - Ubuntu 119mb and alpine 13.1mb
   - alpine is smaller because it only downloads essentials dependencies not whole OS
4. Inspect an image — what information can you see?
   - docker inspect nginx
   - shows layers,config ,environment and many more info about image
5. Remove an image you no longer need
   - docker rmi <image_id>

## Task 2: Image Layers
1. Run docker image history nginx — what do you see?
  - it creates layers of each command of dockerfile
  - It shows:
    - Layer 1 → base image  
    - Layer 2 → install packages  
    - Layer 3 → config  
2. Each line is a layer. Note how some layers show sizes and some show 0B
    - Layers are a stack of read-only filesystem changes, where each Dockerfile instruction creates a new "slice."
    - 0B layers occur because metadata-only commands (like ENV or EXPOSE) don't add physical files to the image.
3. Write in your notes: What are layers and why does Docker use them?
    - Docker uses them to save disk space by sharing identical layers between images and to speed up builds using caching.

## Task 3: Container Lifecycle
1. Create a container (without starting it)
  - docker create nginx
2. Start the container
  - docker start <container_id>
3. Pause it and check status
  - docker pause <container_id>
  - docker ps -a
4. Unpause it
  - docker unpause <container_id>
5. Stop it
  - docker stop <container_id>
6. Restart it
  - docker restart <container_id>
7. Kill it
  - docker kill <container_id>
8. Remove it
  - docker rm <container_id>

## Task 4: Working with Running Containers
1. Run an Nginx container in detached mode
   - docker run -d -p 80:80 nginx
2. View its logs
   - docker logs <nginx_container_id>
3. View real-time logs (follow mode)
   - docker logs <nginx_container_id> -f
4. Exec into the container and look around the filesystem
   - docker exec -it <container_id> bash
5. Run a single command inside the container without entering it
   - docker exec <container_id> ls
   - docker exec <container_id> whoami 
6. Inspect the container — find its IP address, port mappings, and mounts
   docker inspect <container_id>

## Task 5: Cleanup
1. Stop all running containers in one command
   - docker stop $(docker ps -q)
2. Remove all stopped containers in one command
   - docker rm $(docker ps -aq)
3. Remove unused images
   - docker rmi <image_id>
4. Check how much disk space Docker is using
   - docker system df


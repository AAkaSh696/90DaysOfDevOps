## Day 29 – Introduction to Docker

## Task 1: What is Docker?
Docker is a tool that lets you to containerized applications 
1. Container is  way to package an application with all necessary dependencies and configuration ,this helps in running an application across different systems or machines without setting it up manually .
2. In virtualization ,resources of same system gets allocated but in containerization resources gets shared.
3. Docker Architecture:
   - DockerFile: Simple text file with instructions to build an image.
   - DockerImage: Single File with all the dependencies and libraries to run the program
   - Containers: Instance of an image
   - Daemon: Persistent background service that manages docker objects(images,containers,networks etc.)
   - Docker Registry: Central repository for storing and distributing docker images
  
- Docker Client → sends commands  
- Docker Daemon → runs containers  
- Images → blueprint  
- Containers → running instance  
- Docker Hub → image store

## Task 2: Install Docker
1. Install Docker on your machine (or use a cloud instance) (Practical)
2. Verify the installation (Practical) 
3. Run the hello-world container (Practical)
4. Read the output carefully — it explains what just happened (Practical)

## Task 3: Run Real Containers
1. Run an Nginx container and access it in your browser (Practical)
2. Run an Ubuntu container in interactive mode — explore it like a mini Linux machine (Practical)
3. List all running containers (Practical)
4. List all containers (including stopped ones) (Practical)
5. Stop and remove a container (Practical)

## Task 4: Explore
1. Run a container in detached mode — what's different? (Practical) -> In this mode it don't shows the processes req. to run container in terminal 
2. Give a container a custom name (Practical)
3. Map a port from the container to your host (Practical)
4. Check logs of a running container (Practical)
5. Run a command inside a running container (Practical)

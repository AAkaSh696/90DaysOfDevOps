## Day 36 – Docker Project: Dockerize a Full Application

- I chose node.js + mongodb database app because it one of the  widely used combo in companies

## Dockerfile
  Taking node:18-alpine base image to reduce size
- FROM node:18-alpine
  
  Creating a working directory in container
- WORKDIR /app

  Copying necessary dependencies in container directory /app
- COPY package*.json .

  Used to download and manage code libraries (packages) for Node.js
- RUN npm install

  Copying remaining  files 
- COPY . .

  Adding non-root user for security purpose
- RUN adduser -D alex

  Assigning user
- USER alex

  Indication port 5000
- EXPOSE 5000

  Running the container
- CMD [ "node", "server.js" ]

## Challenges you faced and how you solved them
  - One of the biggest problem is in yml syntax even a small tab space , : or - shows error

## Final image size
- app_size = 248 mb
- mongodb = 1.3gb

## Docker hub link
https://hub.docker.com/repository/docker/aakash969/day-36-task-app/general

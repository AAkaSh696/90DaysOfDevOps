## Day 37 – Docker Revision

## Self-Assessment Checklist
Note: Icons for 
- can do ✅
- shaky ⚠️
- haven't done ❌
---

 - Run a container from Docker Hub (interactive + detached) ✅
 - List, stop, remove containers and images ✅
 - Explain image layers and how caching works ✅
 - Write a Dockerfile from scratch with FROM, RUN, COPY, WORKDIR, CMD ✅
 - Explain CMD vs ENTRYPOINT ✅
 - Build and tag a custom image ✅
 - Create and use named volumes ✅
 - Use bind mounts ✅
 - Create custom networks and connect containers ✅
- Write a docker-compose.yml for a multi-container app ✅
 - Use environment variables and .env files in Compose ✅
 - Write a multi-stage Dockerfile ✅
- Push an image to Docker Hub ✅
 - Use healthchecks and depends_on ✅

## Quick-Fire Questions
1. Image is blueprint that contains everything needed to run an application and container is live , running instance of that image.
2. Data inside the container gets permanently deleted if we didn't attach or bind local storage to it.
3. When you create a custom bridge network (using docker network create my-net), Docker provides a built-in Internal DNS server (Google).
4. docker compose down- stops and removes running containers and networks but leaves volumes intact which means database or app data will still be there but docker compose down -v : stops and removes running containers,networks and volumes as well.
5. Multi-stage builds helps to reduce the size of image.
6. COPY: copies the data from local to image and ADD: downloads data from url and put it to image.
7. -p 8080:80 means map local port 8080 to container port 80.
8. docker system df.

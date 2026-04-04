## Day 33 – Docker Compose: Multi-Container Basics

*Note: For practical refer to images on github or linkedin*

## Task 1: Install & Verify
(Practical)

## Task 2: Your First Compose File
(Practical)

## Task 3: Two-Container Setup
(Practical)
- Yes, the data is still there because we use named volume i.e., adds local database to it so MYSQL data is stored outside container

## Task 4: Compose Commands
docker compose up -d        # run in background
docker compose ps          # list services
docker compose logs        # logs
docker compose logs mysql    # logs of specific service
docker compose stop        # stop containers
docker compose down        # remove everything
docker compose up --build  # rebuild

## Task 5: Environment Variables
(Practical)

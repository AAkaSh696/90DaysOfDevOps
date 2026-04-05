## Day 34 – Docker Compose: Real-World Multi-Container Apps

## Task 1: Build Your Own App Stack
( Refer to 90DaysOfDevOps/2026/day-34/day-34-app/app for app and Dockerfile )

## Task 2:depends_on & Healthchecks & Task 3: Restart Policies
( Refer to  90DaysOfDevOps/2026/day-34/day-34-app for docker-compose.yml )

- App waits until DB is READY (not just started)
- After manully killed (docker kill <container_id> : yes , DB restart automatically
- always: always restart and on-failure: restart only if error

## Task 4: Custom Dockerfiles in Compose
( Refer to  90DaysOfDevOps/2026/day-34/day-34-app for docker-compose.yml )
- Rebuild and restart with one command: docker compose up --build

## Task 5: Named Networks & Volumes
( Refer to  90DaysOfDevOps/2026/day-34/day-34-app for docker-compose.yml )

## Task 6: Scaling (Bonus)
1. Try scaling your web app to 3 replicas using docker compose up --scale
- docker compose up --scale web=3
2. Port conflicts arises ( 5000 already used by one container)
3. Multiple containers can't bind same port on host


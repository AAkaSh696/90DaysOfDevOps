## Day 39 – What is CI/CD?

## Task 1: The Problem
1. What can go wrong?
- Code conflicts between developers
- Bugs reaching production
- Manual mistakes during deployment
- Different environments causing failures
- No proper testing before deployment

2. What does "it works on my machine" mean and why is it a real problem?
- It means the code or app works on a developer’s local system but fails in other environments (server, production) due to differences in configuration, dependencies, or OS.

3. How many times a day can a team safely deploy manually?
- Very limited (1–2 times a day)
- Manual deployment is slow and risky
- Not scalable for growing teams

## Task 2: CI vs CD
1. Continuous Intergeration
- Developers frequently push code to a shared repository and each push triggers automated build and tests to catch bugs early.
- Example: A developer pushes code → tests run automatically → errors are detected immediately.

2. Continuous Delivery
- Code is always kept ready for deployment after passing all tests. In this deployment is still a manual decision.
- Here, delivery means that it requires a manual click for deployment .
- Example: Code is tested and built → ready to deploy → team decides when to release.

3. Continuous Deployment
- Every change that passes tests is automatically deployed to production.
- In this , it don't requires manual click for deployment , it automatically deploys code or app to production.
- Example: Push code → tests pass → automatically deployed to live users.

## Task 3: Pipeline Anatomy
- **Trigger** → Event that starts pipeline (push, pull request)
- **Stage** → Phase like build, test, deploy
- **Job** → A group of steps inside a stage
- **Step** → Single command or action
- **Runner** → Machine that executes jobs (GitHub runner or self-hosted)
- **Artifact** → Output (build files, Docker image)

## Task 4: Pipeline Diagram
![WhatsApp Image 2026-04-13 at 15 16 30](https://github.com/user-attachments/assets/7019c3fc-3612-4930-8f82-5de3b937030b)

## Task 5: Explore in the Wild
Gitub Repo: https://github.com/remsky/Kokoro-FastAPI/blob/master/.github/workflows/release.yml

1. What triggers it?
- on push branch release
- workflow_dispatch

2. How many jobs does it have ?
- It has 4 jobs ( prepare-release, build-images,  create-manifests, create-release)

3. What does it does?
- Prepare , Release and Publish Docker images

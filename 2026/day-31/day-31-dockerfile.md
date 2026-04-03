## Day 31 – Dockerfile: Build Your Own Images

** Note : For practical go through images either on github on linkedin

## Task 1: Your First Dockerfile
(Practical)

## Task 2: Dockerfile Instructions
(Practical)

## Task 3: CMD vs ENTRYPOINT
(Practical)
- In CMD , commands gets overriden but  In ENTRYPOINT commands  don't overridden, it appends arguments
- I use ENTRYPOINT for the core command that must always run, and CMD for the default arguments that users can override

## Task 4: Build a Simple Web App Image
(Practical)

## Task 5: .dockerignore
(Practical)

## Task 6: Build Optimization
Layer order matters because Docker uses top-down caching: if we change a single line in your Dockerfile, every layer below it must be completely rebuilt from scratch.To maximize speed, we should place stable commands (like installing OS packages) at the top and frequent changes (like your application code) at the bottom.

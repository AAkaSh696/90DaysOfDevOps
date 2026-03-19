## Day 23 – Git Branching & Working with GitHub

## Task 1: Understanding Branches
1. A branch is a separate line of development that lets work on new features without affecting the main code.
2. To test code and then merged safely , if everyone commits directly to main, problems occur.
3. HEAD is a pointer that tells Git where you currently are.
4. Git changes the working directory files to match that branch.

## Task 2: Branching Commands — Hands-On
1. git branch
2. git branch feature-1
3. git switch feature-1
4. git checkout -b feature-2
5. git checkout :	old command while git switch : modern branch switch command
6. (Practical)
7.  (Practical)
8. git branch -d feature-2

## Task 3: Push to GitHub
1. (Practical)
2. P
3. P 
4. P
5. (Practical)
6. origin is your fork; upstream is the original project you forked from.
To link them, run: git remote add upstream <original-repo-url>.
To sync, run: git fetch upstream then git merge upstream/main

## Task 4: Pull from GitHub
1. (Pracrical)
2.  (Practical)
3.  - git fetch:  Downloads changes only 
    - git pull:   Downloads + merges     

## Task 5: Clone vs Fork
1. (Practical)
2.  (Practical)
3. - Clone downloads a repository to your computer while Fork creates your own copy of someone else's repository on GitHub.
- Clone use when : Your own repo             
- Fork use when : Contributing to open-source 
- By tapping sync fork button on github

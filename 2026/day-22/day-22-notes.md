## Day 22 – Introduction to Git: Your First Repository

## Task 1 — Install and Configure Git

1. Check Git installation
- git --version

2. Configure Git identity
- git config --global user.name "Your Name"
- git config --global user.email "your@email.com"

3. Verify configuration
- git config --list

## Task 2 — Create Your Git Project

1. Create project folder
- mkdir devops-git-practice
- cd devops-git-practice
  
2. Initialize Git repository
- git init
 
3. Check repository status
- git status

4. Explore `.git` folder
- ls -a

It contains folders like hook ref etc.
This folder stores **all Git history**.

## Task 3 — Create Git Commands Reference

1. Create a file:
- touch git-commands.md

# Git Commands Reference

## Setup & Config

- git config --global user.name :
Sets your Git username

Example:
git config --global user.name "Aakash"

- git config --global user.email :
Sets your email for commits

Example:
git config --global user.email "aakash@email.com"

## Basic Workflow

- git init :
Creates a new Git repository

Example:
git init

- git add :
Stages files for commit

Example:
git add git-commands.md

- git commit :
Saves changes to repository history

Example:
git commit -m "Add git commands reference"

## Viewing Changes

- git status :
Shows repository status

Example:
git status

- git log :
Shows commit history

Example:
git log

## Task 4 — Stage and Commit

1. Stage file
- git add git-commands.md

2. Check staged files
- git status

3. Commit
- git commit -m "Add initial git commands reference"

4.View commit history
- git log

## Task 5 — Build Commit History
- git log --oneline :
Shows compact commit history

- git diff :
Shows file changes

## Task 6: Understand the Git Workflow

1. git add moves changes to the staging area.
   git commit saves staged changes permanently in Git history.

2. The staging area is a temporary place where changes are prepared before committing.

3. git log shows commit history including commit ID, author, date, and message.

4. The .git folder stores the entire repository history and configuration.
    Deleting it removes Git tracking.
   
5. Working directory vs staging vs repository

- Working directory: project files you edit
- Staging area: prepared changes
- Repository: saved commit history

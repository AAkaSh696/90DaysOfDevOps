## Day 40 – Your First GitHub Actions Workflow

## hello.yml
name: Hello Workflow

on:
    push:
        branches: [main]

jobs:
    greet:
        runs-on: ubuntu-latest
        steps:
            - name: Checkout Code
              uses: actions/checkout@v4

            - name: Print Hello
              run: echo "Hello from Gihtub Actions"

            - name: Print date and time
              run: date

            - name: Print branch name
              run : echo "Branch name is ${{ github.ref_name}}"

            - name: List files
              run: ls -la

            - name: Print Runner's name
              run: echo "Runner is $(uname -o)" 

## Task 3: Understand the Anatomy
- on → defines when the pipeline runs
- jobs → group of tasks
- steps → actual commands executed
- runs-on → defines the runner machine
- uses → to use predefined actions
- run → to execute shell commands

## What does a failed pipeline look like? How do you read the error?
- Failed pipeline shows a red cross mark ❌ , github actions checks step by step and if the pipeline breaks it gives error reason.

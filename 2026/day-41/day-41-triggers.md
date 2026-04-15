# Day 41 – Triggers & Matrix Builds

##  PR Trigger
- Triggered on pull_request to main
- Prints branch name

##  Schedule Trigger
- Runs daily using cron: 0 0 * * *
- Monday 9 AM cron: 0 9 * * 1

##  Manual Trigger
- Used workflow_dispatch
- Took environment input (staging/production)

##  Matrix Build
- Ran jobs across:
  - 2 OS (Ubuntu, Windows)
  - 3 Python versions
- Total jobs: 5 (after exclude)

##  Fail-Fast
- true → stops all jobs on failure
- false → runs all jobs even if one fails

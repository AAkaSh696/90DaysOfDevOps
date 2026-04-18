# Day 43 – Jobs, Steps, Env Vars & Conditionals

## Multi Job Workflow
Used multiple jobs with dependencies:
- build → test → deploy
- Used `needs` to define execution order

## Environment Variables
Used at 3 levels:
- Workflow level → APP_NAME
- Job level → ENVIRONMENT
- Step level → VERSION

Also used GitHub context:
- github.sha
- github.actor

## Job Outputs
- Passed data (date) between jobs
- Used outputs and needs

### Why outputs?
Jobs run on different machines, so outputs help pass data between them.

## Conditionals
- Run step only on main branch
- Run step if previous step fails
- Run job only on push
- Used continue-on-error to prevent failure stop

## Smart Pipeline
- Parallel jobs: lint and test
- summary job runs after both
- Detects branch type
- Prints commit message

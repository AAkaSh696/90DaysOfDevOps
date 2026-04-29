## Day 47 – Advanced Triggers: PR Events, Cron Schedules & Event-Driven Pipelines

## The cron expressions from Task 3
- 30 3 * * 1-5
- 0 0 1 * *
- GitHub deprioritises or pauses schedules on inactive repos to save compute resources and prevent unnecessary background runs on dead projects.

## paths vs paths-ignore
| Use          | When                        |
| ------------ | --------------------------- |
| paths        | Run only for specific files |
| paths-ignore | Skip unnecessary runs       |

##  When would an external system (like a Slack bot or monitoring tool) trigger a pipeline?
- Slack button → deploy
- Monitoring alert → restart service
- External system → trigger pipeline

## workflow_run vs workflow_call
- workflow_call → reusable workflows
- workflow_run → chain workflows

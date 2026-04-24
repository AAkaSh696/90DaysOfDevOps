## Day 46 – Reusable Workflows & Composite Actions

## Understand workflow_call
1. A reusable workflow is a GitHub Actions file that can be called by other workflows to eliminate code duplication and centralize maintenance
2. The workflow_call trigger is the GitHub Actions event that allows one workflow to be executed by another, transforming it into a reusable template.
3. While both use the uses: keyword, calling a reusable workflow executes an entire YAML file (including its jobs and runners), whereas a regular action executes a single step within an existing job
4. A reusable workflow must be stored in the .github/workflows directory of a repository to be callable.

## Comparison table
| Feature | Reusable Workflow | Composite Action |
|--------|----------------|----------------|
| Triggered by | workflow_call | uses: |
| Contains jobs | Yes | No |
| Contains steps | Yes | Yes |
| Location | .github/workflows | .github/actions |
| Accept secrets | Yes | No (indirect via env) |
| Best for | Full pipelines | Reusable step logic |

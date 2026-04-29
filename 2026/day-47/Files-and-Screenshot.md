## Task 1
name: Pull request Event 

on:
    pull_request:
        types: [ opened,synchronize,reopened,closed ]

jobs: 
    pr-info:
        runs-on: ubuntu-latest
        steps:
            - name: pr-details
              run: |
                echo " Event type: ${{ github.event.action }}"
                echo " PR title: ${{ github.event.pull_request.title }}"
                echo " PR author: ${{ github.event.pull_request.user.login }}"
                echo " Source Branch: ${{ github.head_ref }}"
                echo " Target Branch: ${{ github.base_ref }}"

            - name: Run when PR merged
              if: github.event.pull_request.merged == true
              run: echo "PR gets merged"

            - name: Updating for testing opened 
              run : echo "Checking 1,2,3"
<img width="950" height="373" alt="image" src="https://github.com/user-attachments/assets/f717401c-a183-4791-a38b-cd339ebfea3f" />
<img width="950" height="373" alt="image" src="https://github.com/user-attachments/assets/b038d267-ce2f-4c8b-abb9-47db19eb15b8" />

## Task 2
name: PR Validation Workflow 

on: 
    pull_request:
        branches: [main]

jobs:
    file-size-check:
        runs-on: ubuntu-latest
        steps:
            - name: Checkout Code
              uses: actions/checkout@v4

            - name: Check file size
              run: |
                LARGE_FILES=$(find . -type f -not -path '*/.*' -size +1M)
                if [ -n "$LARGE_FILES" ]; then
                    echo "Files are larger than 1MB: $LARGE_FILES"
                    exit 1
                fi

    branch-name-check:
        runs-on: ubuntu-latest
        steps:
            - name: Check branch naming convention 
              run: |
                BRANCH_NAME="${{ github.head_ref }}"
                if [[ ! $BRANCH_NAME =~ ^(feature/|fix/|docs/) ]]; then 
                    echo "Invalid branch name: $BRANCH_NAME"
                    exit 1
                fi
    pr-body-check:
        runs-on: ubuntu-latest
        steps:
            - name: Check PR description 
              run: |
                PR_BODY="${{ github.event.pull_request.body }}"
                if [ -z "$PR_BODY" ]; then
                    echo "Warning PR description is empty "
                else
                    echo "PR description is present"
                fi 
<img width="944" height="410" alt="image" src="https://github.com/user-attachments/assets/a160a56c-2b29-41c2-8631-856c8baf1d37" />
<img width="959" height="401" alt="image" src="https://github.com/user-attachments/assets/a743fee3-4c3d-4912-883a-a0c6bd474e01" />

## Task 3
name: Scheduled Workflows

on:
    schedule:
        - cron: '30 2 * * 1'
        - cron: '0 */6 * * *'
    workflow_dispatch:

jobs:
    health-check-job:
        runs-on: ubuntu-latest
        steps:
            - name: Show triggering Schedule
              run: echo "Triggered by cron schedule ${{ github.event.schedule}}"

            - name: Website Health Check
              run: |
                STATUS=$(curl -o /dev/null -s -w "%{http_code}" http://google.com)
                echo "Received Status code : $STATUS"

                if [ "$STATUS" -ne 200 ]; then 
                    echo "Health check failed!"
                    exit 1
                fi
<img width="956" height="415" alt="image" src="https://github.com/user-attachments/assets/1e0da3b2-8cca-4470-aa6e-78a153a20a8d" />

## Task 4
<img width="931" height="473" alt="image" src="https://github.com/user-attachments/assets/86288cdf-0747-4ad1-a362-71e779f379e1" />
<img width="1844" height="874" alt="11" src="https://github.com/user-attachments/assets/a553f12f-d177-47a7-8178-548d635a1a16" />

## Task 5
<img width="944" height="461" alt="image" src="https://github.com/user-attachments/assets/66bf5fd1-a78f-4673-b7e0-2d3c52c2c4d2" />
<img width="1860" height="909" alt="13" src="https://github.com/user-attachments/assets/000a9d4f-de44-40d4-bea2-2b0e579a9138" />
<img width="1919" height="806" alt="14" src="https://github.com/user-attachments/assets/751b30f4-1307-426d-982f-829543912a9a" />

## Task 6
<img width="1872" height="830" alt="15" src="https://github.com/user-attachments/assets/e18a5149-dc66-4c66-b2a3-71c79262fe37" />
<img width="1081" height="344" alt="16" src="https://github.com/user-attachments/assets/f17a40d4-1899-4032-a84c-bfed5568d88f" />
<img width="1915" height="795" alt="17" src="https://github.com/user-attachments/assets/33a030d5-7531-471d-acdb-7627b89380f8" />

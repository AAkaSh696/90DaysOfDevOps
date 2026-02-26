## Day 11 challenge 

## Files and Directories Created
- devops-file.txt
- notes.txt
- project-config.yaml
- app-logs
- heist-project/vault
- heist-project/plans
- heist-project/vault/gold.txt
- heist-project/vault/strategy.conf
- bank-heist/access-codes.txt
- bank-heist/blueprint.pdf
- bank-heist/escape-plan.txt

## Ownership Changes
- devops-file.txt:
   - Before:user ->ec2-user:ec2-user
   - After:user -> tokyo:ec2-user ->berlin:ec2-user
- notes.txt:
   - Before:user ->ec2-user:ec2-user
   - After:user -> ec2-user:heist-team
- project-config.yaml:
   - Before:user ->ec2-user:ec2-user
   - After:user -> professor:heist-team
- app-logs:
   - Before:user ->ec2-user:ec2-user
   - After:user -> berlin:heist-team
-  heist-project/vault and heist-project/plans and heist-project/vault/gold.txt and heist-project/vault/strategy.conf
   - Before:user ->ec2-user:ec2-user
   - After:user -> professor:planners
- bank-heist/access-codes.txt
   - Before:user ->ec2-user:ec2-user
   - After:user -> tokyo:vault-team
- bank-heist/blueprint.pdf
   - Before:user ->ec2-user:ec2-user
   - After:user -> berlin:tech-team
- bank-heist/escape-plan.txt
   - Before:user ->ec2-user:ec2-user
   - After:user -> nairobi:vault-team

## Commands Used
- useradd
- ls -l
- touch
- chown
- chgrp
- groupadd
- mkdir
- ls -ld
- mkdir -p
- ls- lR
- chown -R

## What I learned 
- Every file has both an owner (user) and a group — they control access differently.
- chown can change both owner and group together using owner:group syntax.
- Recursive ownership changes (-R) are essential for managing entire project directories.
- Proper ownership is critical for secure deployments and multi-user environments.
  

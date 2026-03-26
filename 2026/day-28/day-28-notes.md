## Day 28 – Revision Day: Everything from Day 1 to Day 27

## Task 1: Self-Assessment Checklist 
Icons for : 
- Can do confidently ✅
- Need to revisit ⚠️
- Haven't done yet ❌

### Linux
 - Navigate the file system, create/move/delete files and directories ✅
 - Manage processes — list, kill, background/foreground ✅
 - Work with systemd — start, stop, enable, check status of services ✅
 - Read and edit text files using vi/vim or nano ✅
 - Troubleshoot CPU, memory, and disk issues using top, free, df, du ✅
 - Explain the Linux file system hierarchy (/, /etc, /var, /home, /tmp, etc.) ✅
 - Create users and groups, manage passwords ✅
 - Set file permissions using chmod (numeric and symbolic) ✅
 - Change file ownership with chown and chgrp ✅
 - Create and manage LVM volumes ⚠️
 - Check network connectivity — ping, curl, netstat, ss, dig, nslookup ✅
 - Explain DNS resolution, IP addressing, subnets, and common ports ✅
 
### Shell Scripting
 - Write a script with variables, arguments, and user input ✅
 - Use if/elif/else and case statements ✅
 - Write for, while, and until loops ✅
 - Define and call functions with arguments and return values ✅
 - Use grep, awk, sed, sort, uniq for text processing ⚠️
 - Handle errors with set -e, set -u, set -o pipefail, trap ✅
 - Schedule scripts with crontab ✅
 
### Git & GitHub
 - Initialize a repo, stage, commit, and view history ✅
 - Create and switch branches ✅
 - Push to and pull from GitHub ✅
 - Explain clone vs fork ✅
 - Merge branches — understand fast-forward vs merge commit ✅
 - Rebase a branch and explain when to use it vs merge ✅
 - Use git stash and git stash pop ✅
 - Cherry-pick a commit from another branch ✅
 - Explain squash merge vs regular merge ✅
 - Use git reset (soft, mixed, hard) and git revert ✅
 - Explain GitFlow, GitHub Flow, and Trunk-Based Development ✅
 - Use GitHub CLI to create repos, PRs, and issues  ✅
 
 ## Task 2: Revisit Your Weak Spots
 Done task 2 by practicing lvm and text processing commands and learned that this topic needs memorizing syntax and regular practice.

 ## Task 3: Quick-Fire Questions
 Icons for :
 - Own ✅
 - Wrong and google ⚠️
   
 1. chmod 755 script.sh: it means user can rwx while groups and other can r_x. ✅
 2. A process is any running program, while a service is a specific process that runs continuously in the background to perform system tasks. ⚠️
 3. ps aux | grep :8080 ✅
 4. set -euo pipefail: it means exit when an error occurs , unset variable is used ot pipe (|) fail. ✅
 5. git reset --hard : deletes commit permanently while revert undo the commit and creates revert commit ✅
 6. for a team of 5 developers i would you github flow branching strategy ✅
 7. git stash temporarily stores the work and is used when we have to urgently switch to other branch ✅
 8. crontab -e : 0 3 * * * <script_path> ⚠️
 9. git fetch just put the changes in working tree while git pull put and commit changes ✅
 10. LVM(Logical Volume Manager)  turns physical hard drives into a flexible pool of storage.It is used because standard partitions are often rigid and difficult to change once created, whereas LVM is dynamic.⚠️

## Task 4: Organize Your Work
1. Checked that my daily submissions (day-1 through day-27) are committed and pushed
2. git-commands.md is upto date
3. shell scripting cheatsheet is complete
4. Verified your GitHub profile and repos are clean

## Task 5: Teach It Back
- Topic: merge vs squash vs rebase commit mai antar :
Sabse pehle merge commit : maanle tere pe 2 branch hai 'main' aur 'dev' aur to dev ke changes ko main mai laana chahta hai toh tu iss 
branch ko merge karega ( git merge dev ) toh 'dev' ke changes 'main' mai aa jayenge aur ek merge commit ban jayega jo batayega ki tune merge kiya hai .
Ab rebase : dekh rebase(git rebase main) hota ye hai ki ye dono branches ke commit history ko linear bana deta hai jis se history badhiya lage .
Ab squash : dekh squash(git merge dev --squash)  mai hota ye hai ki maan le tune dev branches mai kayi kaam kare aur har kaam mai ek commit kiya ab tu final commit ke change ko main 
mai laana chahta hai aur chahta hai ki bas last commit hee main mai jaaye 

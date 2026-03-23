## Day 26 – GitHub CLI: Manage GitHub from Your Terminal

## Task 1: Install and Authenticate
1. On Amazon Linux: sudo yum install gh -y
2. gh auth login
3. gh auth status
4. - GitHub.com
   - HTTPS
   - Login via browser

## Task 2: Working with Repositories
1  gh repo create myrepo --public --clone --add-readme
2. gh repo create myrepo --public --clone --add-readme
3. gh repo view <repo_name>
4. gh repo list 
5. gh repo view <repo_name> --web
6. gh repo delete <repo_name>

## Task 3: Issues
1. gh issue create --repo <repo_name> --title " " --body " " --label " "
2. gh issue list --repo <repo_name>
3. gh issue view 1 --repo <repo_name>       # 1 -> PR(Pull request number) 
4. gh issue close 1 --repo <repo_name>
5. Automatically creates issues when:
   - CI/CD pipeline fail
   - build or deployment error occurs

## Task 4: Pull Requests
1. Pull req create: gh pr create --fill
2. gh pr list --repo <repo_name>
3. gh pr view 1 --repo <>
4. gh pr merge 1 --repo <>
5. - gh pr merge --merge , gh pr merge --squash and gh pr merge --rebase
-  Step 1: gh pr view 1
-  Step 2: gh pr checkout 1
-  Step 3: gh pr review 1 --approve
  
## Task 5: GitHub Actions & Workflows (Preview)
1. gh run list
2. gh run view <run-id>
3. gh run helps you monitor and troubleshoot the execution status and logs of your CI/CD runs directly from the terminal,
  while gh workflow lets you easily enable, disable, and manage your GitHub Actions workflows [1].

## Task 6: Useful gh Tricks
- gh api: direct github api calls 
    -  E.g., gh api user
- gh gist: share code snippets quickly.
    - E.g., gh gist create file.txt --public
    - List gists: gh gist list
- gh release: used for versioning(v1.0,v2.0).
    -  E.g., gh releae create v1.0 --title "First Release" --notes "Initial version"
    -  List release: gh release list
    -  Upload file: gh release upload v1.0 file.zip
- gh alias: Creates own custom commands
    -E.g., gh alias set as "auth status"
- gh search repos: Search github
    - E.g., gh search repos docker     

  


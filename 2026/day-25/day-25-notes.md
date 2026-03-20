## Day 25 – Git Reset vs Revert & Branching Strategies

## Task 1: Git Reset — Hands-On
1. Make 3 commits in your practice repo (commit A, B, C)- (Practical)
2. Use git reset --soft to go back one commit — what happens to the changes?- (Practical) ->  Commit C removed and Changes still STAGED
3. Re-commit, then use git reset --mixed to go back one commit — what happens now?- (Practical) ->  Commit removed and  Changes UNSTAGED (back to working directory)
4. Re-commit, then use git reset --hard to go back one commit — what happens this time?- (Practical) ->  Commit removed Changes DELETED permanently
5. - --soft  → keeps changes staged
     ,--mixed → keeps changes unstaged
     ,--hard  → deletes everything
   - hard (because it deletes code permanently)
   - --soft  → fix last commit message
     ,--mixed → redo commit properly
     ,--hard  → discard unwanted work completely
   - No, but just only when it necessarily needed

## Task 2: Git Revert — Hands-On
1. Make 3 commits (commit X, Y, Z)- (Practical)
2. Revert commit Y (the middle one) — what happens?- (Practical) -> New commit created , Commit Y still exists in history and  Changes undone safely
3. Check git log : Yes ,commit Y is still in history
4. - reset  → deletes history while revert → preserves history
   - Because it does NOT rewrite history
   - reset  → local mistakes while revert → production/shared code fixes

## Task 3: Reset vs Revert — Summary

git reset        | git revert
-----------------|-------------------------
Moves HEAD back  | Creates new undo commit
Yes (removes)    | No (keeps history)
Not safe         | Safe for shared branches
Local fixes      | Production fixes

## Task 4: Branching Strategies
1. Gitflow:
  main ──────────────── production
  develop ───────────── active dev
   ├── feature/*
   ├── release/*
   └── hotfix/*
Use Case : Large teams, structured releases.
Pros:  Organized and Stable releases
Cons: Complex and Slow

2. Github Flow:
   main
 └── feature branch → PR → merge → deploy
Use Case: Startups, fast deployment
Pros: Simple and Fast
Cons: Less control for big releases

3. Trunk-Based Development:
   main (everyone commits frequently)
Use Case: High-speed CI/CD environments
Pros: Very fast and Less merge conflicts
Cons: Requires strong discipline

4. - GitHub Flow for startups
   - GitFlow for large team
   - Not quiet but may be K8s and React

 ## Task 5: Git Commands Reference Update
 - Setup & Config
   - Initialize Git: git init -> Initialize a new Git repository
   - Configure Username: git config --global user.name "Your Name"
   - Configure Email: git config --global user.email "your@email.com"
   - Check Config: git config --list
- Basic WorkfAdd Remotelow
   - Check Status: git status
   - Add Files: git add file.txt or git add .
   - Commit Changes: git commit -m "message"
   - View Logs:
               - git log
               - git log --oneline
               - git log --oneline --graph --all
     - View Changes: git diff
  - Branching
    - List Branches: git branch
    - Create Branch: git branch feature-1
    - Switch Branch: git switch feature-1
    - Create & Switch: git switch -c feature-1
    - Delete Branch: git branch -d feature-1
  - Remote
    - Add Remote: git remote add origin <repo-url>
    - View Remote: git remote -v
    - Push Code: git push -u origin main
    - Pull Changes: git pull origin main
    - Fetch Changes: git fetch
    - Clone Repository: git clone <repo-url>
  - Merging & Rebasing
    - Merge Branch: git merge feature-1
    - Squash Merge: git merge feature-1 --squash
    - Rebase Branch: git rebase main
  - Stash & Cherry Pick
    - Save Work: git stash
    - List Stashes: git stash list
    - Apply Stash: git stash apply <stash_id>
    - Apply & Remove: git stash pop
    - Apply Specific Commit: git cherry-pick <commit-id>
  - Reset & Revert
    - Soft Reset: git reset --soft <commit-id>
    - Mixed Reset: git reset --mixed <commit-id>
    - Hard Reset: git reset --hard <commit-id>
   - 

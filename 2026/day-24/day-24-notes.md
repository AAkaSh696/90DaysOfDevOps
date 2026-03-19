## Day 24 – Advanced Git: Merge, Rebase, Stash & Cherry Pick

** NOTE: For practical , refer to images on linkedin **

## Task 1: Git Merge — Hands-On
1. Create a new branch feature-login from main, add a couple of commits to it-(Practical)
2. Switch back to main and merge feature-login into main-(Practical)
3. Observe the merge — did Git do a fast-forward merge or a merge commit?  In this case ,main didn’t change meanwhile so its fast-forward merge.
4. Now create another branch feature-signup, add commits to it — but also add a commit to main before merging-(Practical)
5. Merge feature-signup into main — what happens this time?-(Practical)  -> this time Git creates a merge commit.
6. - Git simply moves the branch pointer forward because no divergence exists.
   - When both branches have new commits and histories diverge.
   - When the same line of the same file is edited in two branches.
     Git cannot decide which change to keep.

## Task 2: Git Rebase — Hands-On
1. Create a branch feature-dashboard from main, add 2-3 commits-(Practical)
2. While on main, add a new commit (so main moves ahead)-(Practical)
3. Switch to feature-dashboard and rebase it onto main-(Practical)
4. Observing git log --oneline --graph --all : history looks cleaner than merge
5. - Reapplies commits from one branch on top of another.
   - In merge: branch lines remain visible while In rebase: linear history
   - It rewrites history and can break other developers' repositories.
   - Before merging feature branches to keep history clean.
  
## Task 3: Squash Commit vs Merge Commit
1. Create a branch feature-profile, add 4-5 small commits-(Practical)
2. Merge it into main using --squash — what happens? (Practical) -> latest changes addes to main
3. Check git log: only 1 commit added to log 
4. Now create another branch feature-settings, add a few commits-(Practical) 
5. Merge it into main without --squash (regular merge) — compare the history-(Practical) -> Now multiple commit added to log 
6. - Combines multiple commits into a single commit before merging.
   - Use squash merge to keep history clean by combining all changes into one commit, and regular merge to preserve the full commit history of a branch.
   - clean history but original commit details are lost
  
## Task 4: Git Stash — Hands-On
1. Start making changes to a file but do not commit-(Practical)
2. you need to urgently switch to another branch - (Practical) -> Git may block switch
3. Use git stash to save your work-in-progress- (Practical)
4. Switch to another branch, do some work, switch back-(Practical)
5. Apply your stashed changes using git stash pop-(Practical)
6. Try stashing multiple times and list all stashes-(Practical)
7. Try applying a specific stash from the list-(Practical)
8. - git stash pop → apply + remove stash while git stash apply → apply but keep stash
   - When you must quickly switch tasks without committing unfinished work.

## Task 5: Cherry Picking
1. Create a branch feature-hotfix, make 3 commits with different changes-(Practical)
2. Switch to main-(Practical)
3. Cherry-pick only the second commit from feature-hotfix onto main-(Practical)
4. Verify with git log that only that one commit was applied-(Practical)
5. - Cherry-pick copies one specific commit from another branch.
   - Applying a bug fix to production without merging the entire feature branch.
   - Duplicate commits or conflicts.

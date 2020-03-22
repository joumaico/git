# **📌 Git Cheat Sheet**

## **1️⃣ Setting Up a Repository**
**Scenario:** You want to create a new Git repository in a folder.  
```bash
git init
```  
🔹 Initializes a new Git repository in the current directory.

**Scenario:** You want to clone an existing repository.  
```bash
git clone <repo-url>
```  
🔹 Clones a remote repository to your local machine.

---

## **2️⃣ Working with Files & Staging Changes**
**Scenario:** You modified files and want to see which ones changed.  
```bash
git status
```  
🔹 Shows the status of modified, staged, and untracked files.

**Scenario:** You want to stage a specific file for commit.  
```bash
git add <file-name>
```  
🔹 Adds a file to the staging area.

**Scenario:** You want to stage all modified and new files.  
```bash
git add .
```  
🔹 Stages all modified and untracked files in the repository.

**Scenario:** You want to unstage a file but keep changes.  
```bash
git restore --staged <file-name>
```  
🔹 Removes a file from the staging area without deleting changes.

---

## **3️⃣ Committing Changes**
**Scenario:** You want to commit staged changes with a message.  
```bash
git commit -m "Your commit message"
```  
🔹 Commits staged changes with a descriptive message.

**Scenario:** You want to modify the last commit message (before pushing).  
```bash
git commit --amend -m "Updated message"
```  
🔹 Edits the last commit message.

---

## **4️⃣ Synchronizing with Remote (Fetch, Pull, Push)**
**Scenario:** You want to fetch updates from the remote repository without merging.  
```bash
git fetch origin
```  
🔹 Retrieves the latest changes but does not merge them.

**Scenario:** You want to pull remote changes and merge them with your local branch.  
```bash
git pull origin main
```  
🔹 Fetches and merges `origin/main` into the current branch.

**Scenario:** You want to pull updates but rebase your local commits instead of merging.  
```bash
git pull --rebase origin main
```  
🔹 Fetches remote changes and applies them before your local commits (avoids merge commits).

**Scenario:** You want to push your local changes to the remote repository.  
```bash
git push origin main
```  
🔹 Pushes commits to `origin/main`.

---

## **5️⃣ Branching & Merging**
**Scenario:** You want to create a new branch and switch to it.  
```bash
git checkout -b new-branch
```  
🔹 Creates and switches to `new-branch`.

**Scenario:** You want to switch to an existing branch.  
```bash
git checkout branch-name
```  
🔹 Switches to `branch-name`.

**Scenario:** You want to delete a local branch that is already merged.  
```bash
git branch -d branch-name
```  
🔹 Deletes `branch-name` if it has been merged.

**Scenario:** You want to merge another branch into your current branch.  
```bash
git merge branch-name
```  
🔹 Merges `branch-name` into the current branch.

**Scenario:** You want to merge changes while keeping history cleaner (no fast-forward).  
```bash
git merge --no-ff branch-name
```  
🔹 Merges `branch-name` but keeps a separate merge commit.

---

## **6️⃣ Handling Merge & Rebase Conflicts**
**Scenario:** You tried to merge but got conflicts. You want to resolve them and continue.  
```bash
git status
```  
🔹 Shows which files have conflicts.  
Manually edit conflicting files  
```bash
git add <resolved-file>
```  
```bash
git merge --continue
```  
🔹 Resolves merge conflicts and completes the merge.

**Scenario:** You want to cancel a merge due to conflicts.  
```bash
git merge --abort
```  
🔹 Cancels the merge process and restores the original state.

---

## **7️⃣ Undoing Changes & Fixing Mistakes**
**Scenario:** You want to undo changes in a file before staging.  
```bash
git restore <file-name>
```  
🔹 Reverts the file to the last committed state.

**Scenario:** You want to undo a commit but keep the changes.  
```bash
git reset --soft HEAD~1
```  
🔹 Removes the last commit but keeps the changes in the staging area.

**Scenario:** You want to undo a commit and discard the changes.  
```bash
git reset --hard HEAD~1
```  
🔹 Removes the last commit and deletes changes.

---

## **8️⃣ Stashing Changes**
**Scenario:** You need to temporarily save your work without committing.  
```bash
git stash
```  
🔹 Saves changes and restores a clean working directory.

**Scenario:** You want to reapply the last stash.  
```bash
git stash pop
```  
🔹 Reapplies the latest stashed changes.

**Scenario:** You want to see all stashes.  
```bash
git stash list
```  
🔹 Displays all stored stashes.

---

## **9️⃣ Debugging & Recovering Lost Work**
**Scenario:** You accidentally deleted a branch and need to recover it.  
```bash
git reflog
```  
🔹 Shows the commit history, including references to deleted branches.  
Find the commit hash  
```bash
git checkout -b branch-name <commit-hash>
```  
🔹 Uses `reflog` to recover a lost branch.

**Scenario:** You want to find out which commit introduced a bug.  
```bash
git bisect start
```  
```bash
git bisect bad
```  
```bash
git bisect good <commit-hash>
```  
🔹 Starts a binary search to find the faulty commit.

---

## **🔟 Force Push & History Rewriting (Use with Caution!)**
**Scenario:** You need to force push your changes (DANGEROUS).  
```bash
git push --force
```  
🔹 Overwrites remote history (use with caution).

**Scenario:** You want to force push but prevent overwriting new remote changes.  
```bash
git push --force-with-lease
```  
🔹 Ensures no unexpected remote updates are lost.


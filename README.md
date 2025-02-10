# Git Cheat Sheet

## 🛠 Setup & Configuration

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global core.editor "vim"
git config --list
git help config  # Get help on config options
```

## 📁 Initialize & Clone

```bash
git init  # Initialize a new repository
git clone <repo_url>  # Clone a repository
git clone --depth=1 <repo_url>  # Clone only latest commits
```

## 📌 Basic Commands

```bash
git status  # Check status
git add <file>  # Stage a file
git add .  # Stage all changes
git commit -m "Commit message"  # Commit changes
git commit --amend  # Edit last commit
git log  # View commit history
git log --oneline --graph --all  # Compact commit history
git show <commit>  # Show commit details
git diff  # Show unstaged changes
git diff --staged  # Show staged changes
```

## 🌳 Branching & Merging

```bash
git branch  # List branches
git branch <branch_name>  # Create a branch
git checkout <branch_name>  # Switch branch
git checkout -b <branch_name>  # Create and switch to new branch
git merge <branch_name>  # Merge branch
git rebase <branch_name>  # Rebase branch
git cherry-pick <commit>  # Apply a specific commit
git branch -d <branch_name>  # Delete branch
git branch -D <branch_name>  # Force delete branch
```

## 📤 Working with Remote Repositories

```bash
git remote add origin <url>  # Add a remote repository
git remote -v  # View remote URLs
git push -u origin <branch>  # Push changes
git push origin --delete <branch>  # Delete remote branch
git pull origin <branch>  # Pull latest changes
git fetch origin  # Fetch changes without merging
git remote prune origin  # Remove deleted remote branches locally
```

## 🏷️ Staging & Ignoring Files

```bash
git reset <file>  # Unstage file
git reset --hard <commit>  # Reset to a previous commit
git rm --cached <file>  # Remove from tracking
git update-index --assume-unchanged <file>  # Ignore file changes
git update-index --no-assume-unchanged <file>  # Track file changes again
echo "file.txt" >> .gitignore  # Ignore a file
```

## 🛑 Undo & Fixes

```bash
git revert <commit>  # Undo a commit
git reset --soft <commit>  # Move HEAD, keep changes
git reset --mixed <commit>  # Move HEAD, unstage changes
git reset --hard <commit>  # Move HEAD, discard changes
git stash  # Save changes for later
git stash pop  # Reapply stashed changes
git stash list  # View stashed changes
git stash drop  # Delete stash
```

## 🔍 Reviewing Changes

```bash
git diff  # Show unstaged changes
git diff --staged  # Show staged changes
git blame <file>  # Show who changed what
git show <commit>  # Show commit details
git reflog  # View history of HEAD
git bisect start  # Start binary search for a bug
git bisect bad  # Mark current commit as bad
git bisect good <commit>  # Mark commit as good
git bisect reset  # Reset bisecting process
```

## 🔗 Submodules

```bash
git submodule add <repo_url>  # Add submodule
git submodule update --init --recursive  # Initialize submodules
git submodule foreach git pull origin master  # Update all submodules
git submodule deinit -f <submodule>  # Deinitialize submodule
git rm -rf <submodule>  # Remove submodule
```

## 🚀 Git Hooks

```bash
.git/hooks/pre-commit  # Runs before committing
git config core.hooksPath <path>  # Set custom hooks directory
```

## 🏗️ Advanced Commands

```bash
git archive --format=zip --output=repo.zip HEAD  # Create archive
git tag -a v1.0 -m "Version 1.0"  # Create a tag
git push origin --tags  # Push tags
git fsck  # Check repository integrity
git gc  # Cleanup unnecessary files
git worktree add <path> <branch>  # Work with multiple working trees
```

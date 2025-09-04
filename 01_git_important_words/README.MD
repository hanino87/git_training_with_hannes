# Git Basics for Beginners

This guide explains essential Git commands and concepts in simple terms.

---

## 1. Remote
A repository hosted online (GitHub, GitLab, etc.) connected to your local repo.

## 2. Local 
Your repository copy on your own computer.

## 3. `git clone`
Create a copy of a remote repository on your computer.

```bash
git clone <repository-url>

```

## 4. `git pull`
Update your local branch with the latest changes from the remote main bransch.

```bash
git pull origin main

```
## 5. git add
Stage changes (new or modified files) for the next commit.

```bash
git add <file>
git add .   # stage all changes in the directory you stand in the terminal 

```
## 6. git commit
Save staged changes to your local repository with a message.

```bash
git commit -m "Describe your changes"

```

## 7. git push 

Send your local commits to the remote repository

```bash
git push origin main

```

## 8. git stash 

Temporarily save uncommitted changes to switch tasks safely. 

```bash

git stash
git stash pop  # restore later

```

## 9. git merge 

Combine changes from another branch into your current branch.

```bash
git checkout main
git merge feature-branch
```
## 10. Fork

A personal copy of someone else’s repository to make changes safely. 

## 11. repo 

Shortname for respitory 

## 12. Branch
A separate line of development. Useful for working on new features safely.

```bash
git checkout -b feature-branch # create and switch to a new bransch 
git checkout main # switch to an existing branch 
```
## 13. Diffrence between `origin` and `remote` when you Fork

When you fork a repository on GitHub, a copy of the original project is created in your own account.

- **origin**: Points to your own fork (your copy). When you run `git push`, changes are sent here.  
- **upstream (remote)**: Points to the original repository you forked from. Used to fetch updates from the original (`git fetch upstream` and `git merge upstream/main or simpler command with git pull <remote>` <branch>` ).

```bash
git pull class_repo main
```

In short: `origin` = your fork, `upstream` = original repo.

## 14. Connect your fork to the upstream after forking from GitHub

After forking a repository on GitHub, you can connect your local fork to the original repository (upstream) to keep it up to date.

### Steps:

1. **Check current remotes**:
   ```bash
   git remote -v
   ```

2. **Add the upstream remote (the original repository)**:

git remote add <remote> https://github.com/ORIGINAL_OWNER/REPO_NAME.git

3. **Get the latest update from the original repo to your local fork repo**: 

 ```bash
git pull <remote> main
 ```


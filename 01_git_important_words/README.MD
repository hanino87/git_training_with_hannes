# Git Basics for Beginners

This guide explains essential Git commands and concepts in simple terms.

---

## 1. `Remote`
A repository hosted online (GitHub, GitLab, etc.) connected to your local repository.

## 2. `Local`
Your repository copy on your own computer.

## 3. `Git clone`
Create a copy of a remote repository on your computer.

```bash
git clone <repository-url>

```

## 4. `Branch`
A separate line of development. Useful for working on new features safely.


## 5. `Git pull`
Update your local branch with the latest changes from the remote main bransch.

```bash
git pull origin main

```
## 6. `Git add`
Stage changes (new or modified files) for the next commit.

```bash
git add <file>
git add .   # stage all changes in the directory you stand in the terminal 

```
## 7. `Git commit`
Save staged changes to your local repository with a message.

```bash
git commit -m "Describe your changes"

```

## 8. `Git push`

Send your local commits to the remote repository

```bash
git push origin main

```

## 9. `Git stash`

Temporarily save uncommitted changes to switch tasks safely. 

```bash

git stash
git stash pop  # restore later

```
## 10. `Create and change branch`

```bash
git checkout -b feature-branch # create and switch to a new bransch 
git checkout main # switch to an existing branch 

```

## 11. `Git merge`

Combine changes from another branch into your current branch.

```bash
git checkout main
git merge feature-branch
```
## 12. `Fork`

A personal copy of someone else’s repository to make changes safely. 

## 13. `Repo`

Shortname for respitory 


## 14. SSH Key & HTTPS authentication

### SSH Key
An SSH key is a cryptographic key pair used to securely connect to GitHub without entering your username and password every time. It allows Git to authenticate you automatically.

### HTTPS
HTTPS is a URL scheme for Git that uses your GitHub username and password (or personal access token) for authentication each time you push or pull. It's simpler to set up but requires credentials for every operation.


## 15. Diffrence between `origin` and `remote` when you Fork

When you fork a repository on GitHub, a copy of the original project is created in your own account.

In short: `origin` = your fork, `upstream` = original repo.

- **origin**: Points to your own fork (your copy). When you run `git push`, changes are sent here.  
- **upstream (remote)**: Points to the original repository you forked from. Used to fetch updates from the original (`git fetch upstream` and `git merge upstream/main or simpler command with git pull <remote> <branch> ).

```bash
git pull class_repo main 
```

## 16. Connect your fork to the upstream after forking from GitHub

After forking a repository on GitHub, you can connect your local fork to the original repository (upstream) to keep it up to date.

### Steps:

1. **Check current remotes**:
   ```bash
   git remote -v
   ```

2. **Add the upstream remote (the original repository)**:

git remote add upstream https://github.com/ORIGINAL_OWNER/REPO_NAME.git # without ssh-key 

git remote add upstream git@github.com:ORIGINAL_OWNER/REPO_NAME.git # with ssh-key

3. **Get the latest update from the original repo to your local fork repo**: 

 ```bash
git pull <remote> main
 ```
## 17. Pull request 

Pull Requests
A Pull Request (PR) is a way to propose changes to a project.

When you create a PR, you’re asking the project maintainers to review and merge your code into the main branch

## 18. Git Ignore 

A file that stops the files/folders you don`t want to push to remote on GitHub 


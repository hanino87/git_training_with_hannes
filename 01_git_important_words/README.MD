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



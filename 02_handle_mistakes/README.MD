# Git Mistakes and How to Fix Them

Git can feel unforgiving at times, but almost everything can be recovered.  
Here are some common mistakes and how to solve them.

# Tips to Avoid Mistakes

- Run `git status` often to check where you are.  
- Always work in feature branches (`feature/...`, `bugfix/...`) or local branch instead of directly in `main`.  
- Use `git stash` when unsure of you want saving changes or not. 
- Check which branch you are in always to avoid that you are in wrong branch 
- Always when you start working do git pull in your local main branch to allways be in sync to the remote main branch. 

```bash

git branch 

```
---

## 1. You made changes in the wrong branch and want to discard uncommitted changes to switch branches
Git won’t let you switch branches if you have uncommitted changes.

**Solution save changes temporarily:**
```bash
git stash
git checkout correct-branch
git stash pop   # if you want to re-apply them
```

---

## 2. Undo a commit

Different cases depending on whether you pushed or not:

- **Undo last commit but keep changes locally:**
```bash
git reset --soft HEAD~1
```

- **If already pushed but want to remove commit:**
```bash
git revert <commit-hash>
```
👉 `git revert` is safer since it makes a new commit that cancels the changes.

---

## 3. You have 1000+ changed files but only want to commit 3 specific ones to GitHub
You can stage and commit only the files you want.

**1Solution:**
```bash
# Stage only the files you need
git add file1.txt file2.js file3.md

# Commit only those
git commit -m "Commit only 3 files"

# Push to remote
git push origin your-branch
```
**2Solution:**

Implement files that shall not go to the remote repo in the gitignore file. 

```bash

# Stage only the files you need
git add file1.txt file2.js file3.md

# Commit only those
git commit -m "Commit only 3 files"

# Push to remote
git push origin your-branch
```

```


👉 The other files remain uncommitted in your working directory.

---

## 4. Merge conflict between local `main` and remote `main` (branches have diverged)
This happens when both your local `main` and the remote `main` have commits that the other doesn’t.  
Git will stop you from switching branches until the conflict is resolved.

**Solution If you want your local `main` to exactly match remote:**
```bash
git fetch origin
git checkout main
git reset --hard origin/main
```

👉 Once resolved, you can safely switch branches locally.

---


## 5. Mistake: Cloning a Git or fork a repository inside another Git repository

If you accidentally run `git clone` inside an existing Git repository, you end up with a nested Git repository. This can cause confusion with version control, because Git will see the inner repo as a subdirectory but not automatically track it properly.

### How to avoid or fix it:

1. **Avoid nesting**: Always clone/fork repositories in a separate folder outside any existing Git repo.  
2. **Remove the nested repository**: If you accidentally cloned/fork a repo inside another, you can delete it completely:
   ```bash
   rm -rf path/to/nested-repo

---
## 6. Start the day with git pull in main branch.

```bash
git branch 
git checkout main
git pull # use when you have not do forking and want latest changes from your main repo into your local main repo
git pull classrepo main # use if you want the latest changes from the original remote repo to your local fork 
```

---

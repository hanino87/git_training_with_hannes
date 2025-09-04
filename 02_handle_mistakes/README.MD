# Git Mistakes and How to Fix Them

Git can feel unforgiving at times, but almost everything can be recovered.  
Here are some common mistakes and how to solve them.

---

## 1. You committed a file but accidentally ran `git reset --hard` and want to recover it
When you run `git reset --hard`, your working directory and staging area are reset.  
But Git usually still has the history in the **reflog**.

**Solution:**
```bash
# Show recent commits (even "lost" ones)
git reflog

# Find the commit hash before the reset
git checkout <commit-hash>

# Create a new branch or cherry-pick the file
git checkout -b recovered-branch <commit-hash>
```
👉 You can then copy the file back to your current branch.

---

## 2. You made changes in the wrong branch and want to discard uncommitted changes to switch branches
Git won’t let you switch branches if you have uncommitted changes.

**Solution 1 – throw changes away completely:**
```bash
git reset --hard
git clean -fd
```

**Solution 2 – save changes temporarily:**
```bash
git stash
git checkout correct-branch
git stash pop   # if you want to re-apply them
```

---

## 3. Undo a commit

Different cases depending on whether you pushed or not:

- **Undo last commit but keep changes locally:**
```bash
git reset --soft HEAD~1
```

- **Undo last commit and also discard changes:**
```bash
git reset --hard HEAD~1
```

- **If already pushed but want to remove commit:**
```bash
git revert <commit-hash>
```
👉 `git revert` is safer since it makes a new commit that cancels the changes.

---

## 4. You have 1000+ changed files but only want to commit 3 specific ones to GitHub
You can stage and commit only the files you want.

**Solution:**
```bash
# Stage only the files you need
git add file1.txt file2.js file3.md

# Commit only those
git commit -m "Commit only 3 files"

# Push to remote
git push origin your-branch
```

👉 The other files remain uncommitted in your working directory.


## 5. Merge conflict between local `main` and remote `main` (branches have diverged)
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

# Tips to Avoid These Mistakes
- Run `git status` often to check where you are.  
- Always work in feature branches (`feature/...`, `bugfix/...`) or local branch instead of directly in `main`.  
- Use `git stash` when unsure instead of risking `git reset --hard`.
- If you want to use `git reset --hard` check in which branch you are on. If you for example have uncommited changes in a local bransch do not do `git reset --hard` in that bransch. Then you lost all uncommited changes in that branch. 



---

# Git Commands Reference

- [1. Everyday Basics](#1-everyday-basics)
  - [Check Status](#check-status)
  - [Stage Files](#stage-files)
  - [Commit Changes](#commit-changes)
  - [View Commit History](#view-commit-history)
- [2. Branch Work](#2-branch-work)
  - [List All Branches](#list-all-branches)
  - [Create a New Branch](#create-a-new-branch)
    - [Without switching Branch](#without-switching-branch)
    - [With swtiching Branch](#with-swtiching-branch)
  - [Switch to a Branch](#switch-to-a-branch)
  - [Delete a Branch](#delete-a-branch)
- [3. Collaboration (Working with Remote Repos)](#3-collaboration-working-with-remote-repos)
  - [Clone a Repository](#clone-a-repository)
  - [Add a Remote](#add-a-remote)
  - [Check Remote URLs](#check-remote-urls)
  - [Pull Changes from Remote](#pull-changes-from-remote)
  - [Push Changes to Remote](#push-changes-to-remote)
  - [Fetch Changes (Without Merging)](#fetch-changes-without-merging)
- [4. "Oh Shit" Moments (Fixing Mistakes)](#4-oh-shit-moments-fixing-mistakes)
  - [Unstage a File](#unstage-a-file)
  - [Discard Changes to a File](#discard-changes-to-a-file)
  - [Undo Last Commit (Discard Changes)](#undo-last-commit-discard-changes)
  - [Amend Last Commit](#amend-last-commit)
  - [View What Changed in a File](#view-what-changed-in-a-file)
  - [Revert a Commit (Safe Undo)](#revert-a-commit-safe-undo)
  - [Merge Conflicts (Oh Fuck)](#merge-conflicts-oh-fuck)
- [5. Power Moves (Advanced But Useful)](#5-power-moves-advanced-but-useful)
  - [Stash Changes](#stash-changes)
  - [Cherry-Pick a Commit](#cherry-pick-a-commit)
  - [Rebase (Advanced)](#rebase-advanced)
  - [Show Commit Details](#show-commit-details)
  - [Tag a Commit (Version Marking)](#tag-a-commit-version-marking)
- [6. Quick Reference Cheat Sheet](#6-quick-reference-cheat-sheet)
- [7. Common Workflows](#7-common-workflows)
  - [Starting a New Feature](#starting-a-new-feature)
  - [Daily Work Cycle](#daily-work-cycle)
  - [Fixing a Mistake Before Pushing](#fixing-a-mistake-before-pushing)
- [8. Pro Tips](#8-pro-tips)

A beginner-friendly guide to Git commands, organized by how badly you need them right now. <br>
Also with some addtional explainations, if needed.

---

## 1. Everyday Basics

These are the commands you'll use in almost every session. Get comfortable with these first.

### Check Status

**What it does:** Shows you what's changed, what's staged, and what branch you're on.

```bash
git status
```

**When to use it:** All the damn time. Before committing, after making changes, when you're confused about what's going on.

---

### Stage Files

**What it does:** Adds files to the "staging area"—marks them to be included in your next commit.

```bash
git add filename.txt          # Stage a specific file
```

```bash
git add .                     # Stage ALL changes in current directory
```

```bash
git add folder/               # Stage all changes in a folder
```

**When to use it:** After you've made changes and you're ready to commit them.

**Warning:** `git add .` stages EVERYTHING. Make sure you actually want all those changes committed.

---

### Commit Changes

**What it does:** Saves your staged changes with a message describing what you did.

```bash
git commit -m "Your commit message here"
```

**When to use it:** After staging files with `git add`. This creates a snapshot of your work.

**Best practice:** Write clear commit messages like "Add navigation bar" or "Fix typo in homepage" instead of "stuff" or "changes".

---

### View Commit History

**What it does:** Shows you the log of all commits—who made them, when, and what the message was.

```bash
git log                       # Full detailed log
git log --oneline             # Condensed one-line-per-commit view
git log --oneline --graph     # Visual branch graph (cool as hell)
```

**When to use it:** When you need to see what's been done, find a specific commit, or just understand the project history.

---

## 2. Branch Work

Branches let you work on features or tasks without messing up the main code. Essential for team projects and bootcamp assignments.

### List All Branches

**What it does:** Shows all branches in your repo. The one with `*` is your current branch.

```bash
git branch
```

```bash
git branch -a                 # Shows remote branches too
```

**When to use it:** When you need to see what branches exist or confirm which one you're on.

---

### Create a New Branch

#### **Without switching Branch**

**What it does:** Makes a new branch but DOESN'T switch to it yet.

```bash
git branch branch-name
```

**When to use it:** When you want to set up a new branch for a feature or task.

#### **With swtiching Branch**

**What it does:** Creates a new branch and immediately switches to it in one command. This is the most common way to create branches.

```bash
git checkout -b branch-name   # Classic way
git switch -c branch-name     # Newer way (use this one)
```

**When to use it:** 99% of the time when making a new branch—you want to create it and start working on it immediately.

**Example:** For your bootcamp task, you'd do `git switch -c notes-branch` to create and switch to your notes branch.

**What the flags mean:**

- `-c` = "create" (in `git switch`)
- `-b` = "branch" (in `git checkout`)

Both do the same thing, but `git switch -c` is clearer about what it's doing.

---

### Switch to a Branch

**What it does:** Changes your working directory to a different branch.

```bash
git checkout branch-name      # Classic way
git switch branch-name        # Newer, clearer way (use this one)
```

**When to use it:** When you need to work on a different branch.

**Why `git switch` is better:**

`git checkout` is an old command that does WAY too many things—it switches branches, restores files, creates branches, and more. It's like having one Swiss Army knife tool that does 10 different jobs. That makes it confusing for beginners because you have to remember which context you're using it in.

`git switch` was introduced in Git 2.23 (2019) specifically to **only handle branch switching**. It's purpose-built for one job:

- `git switch branch-name` → switch branches
- That's it. Crystal clear.

Meanwhile `git checkout` can:

- Switch branches (`git checkout branch-name`)
- Restore files (`git checkout -- filename`)
- Create and switch branches (`git checkout -b branch-name`)
- Checkout specific commits, tags, etc.

So when you see `git switch`, you KNOW you're dealing with branches. When you see `git checkout`, you have to figure out context. Clearer intent = fewer mistakes.

**Bottom line:** Use `git switch` for branches, use `git restore` for files (covered in "Oh Shit" section). Keep it simple.

---

### Delete a Branch

**What it does:** Removes a branch you don't need anymore.

```bash
git branch -d branch-name     # Safe delete (won't delete if unmerged changes)
git branch -D branch-name     # Force delete (deletes no matter what)
```

**When to use it:** After you've merged a feature branch and don't need it anymore.

**Warning:** `-D` force deletes without checking if changes are merged. Use with caution.

---

## 3. Collaboration (Working with Remote Repos)

These commands sync your local work with GitHub (or whatever remote repo you're using).

### Clone a Repository

**What it does:** Downloads a complete copy of a remote repo to your computer.

```bash
git clone <shh-repository-link>
```

**When to use it:** First time setting up a project on your machine, or when you want to download someone else's repo.

---

### Add a Remote

**What it does:** Links your local repo to a remote repo (like on GitHub).

```bash
git remote add origin <shh-repository-link>
```

**When to use it:** When you've created a local repo and want to push it to GitHub for the first time.

**Note:** `origin` is just a nickname for the remote URL—convention is to call your main remote "origin".

---

### Check Remote URLs

**What it does:** Shows you which remote repos your local repo is connected to.

```bash
git remote -v
```

**When to use it:** When you need to verify where your pushes/pulls are going.

---

### Pull Changes from Remote

**What it does:** Downloads changes from the remote repo and merges them into your current branch.

```bash
git pull
git pull origin branch-name   # Pull from specific branch
```

**When to use it:** When teammates have pushed changes and you need to sync up before continuing work.

**Warning:** Can cause merge conflicts if you and someone else changed the same lines. We'll cover that in "Oh Shit" moments.

---

### Push Changes to Remote

**What it does:** Uploads your local commits to the remote repo.

```bash
git push
```

```bash
git push origin branch-name   # pushes a specific branch to the remote, regardless of which branch you're currently on
```

```bash
git push -u origin branch-name # Push AND set upstream (first time pushing new branch)
```

**When to use it:** After committing changes locally and you're ready to share them with the team or backup to GitHub.

**Note:** The `-u` flag sets up tracking so future `git push` commands know where to go automatically.

---

### Fetch Changes (Without Merging)

**What it does:** Downloads changes from remote but doesn't merge them—lets you review first.

```bash
git fetch
```

**When to use it:** When you want to see what's changed remotely before actually merging it into your work.

---

## 4. "Oh Shit" Moments (Fixing Mistakes)

We all fuck up. Here's how to unfuck things.

### Unstage a File

**What it does:** Removes a file from staging area (undoes `git add`) but keeps your changes.

```bash
git reset filename.txt        # Unstage specific file
git reset                     # Unstage everything
```

**When to use it:** When you accidentally staged something you didn't mean to commit yet.

---

### Discard Changes to a File

**What it does:** Throws away uncommitted changes to a file and reverts it back to exactly how it was in your last commit.

```bash
git checkout -- filename.txt  # Classic way
git restore filename.txt      # Newer way (use this one)
```

**When to use it:** When you've made changes to a file that you **haven't committed yet** and you want to throw them away completely.

**Real scenario example:**

1. Last commit: `index.html` has a blue header
2. You spend 20 minutes changing it to red, adding new divs, etc.
3. You **haven't staged or committed** these changes yet
4. You realize the red header looks terrible
5. You run: `git restore index.html`
6. **File is back to blue header**—all your red header work is gone forever

**Common use cases:**

- **Experimental changes that didn't work out** - Tried something, it sucks, want the old version back
- **Accidentally broke something** - Edited a file and now it's broken, easiest fix is to reset it
- **Started down the wrong path** - Realize you're solving the problem the wrong way, want to start fresh
- **Made changes to the wrong file** - Oops, edited the wrong file by mistake

**Warning:** This DELETES your uncommitted changes permanently. Once you run this, those changes are **gone forever**—they're not in your commit history, not staged, not anywhere. Git can't get them back because you never committed them. It's like editing a Word doc, making changes, then hitting "Revert to Last Saved" without saving first.

**Key distinction:**

- `git restore filename.txt` → Throws away **uncommitted changes** (file goes back to last commit)
- `git reset` → Undoes a **commit** (covered in other sections)
- `git revert` → Creates new commit that undoes an old commit (covered in other sections)

---

### Undo Last Commit (Discard Changes)

**What it does:** Completely removes your last commit AND the changes.

```bash
git reset --hard HEAD~1
```

**When to use it:** When you've made a commit you want to completely erase.

**Warning:** This DELETES work permanently. Only use if you're 100% sure.

---

### Amend Last Commit

**What it does:** Lets you modify your last commit—add more changes or fix the commit message.

```bash
git commit --amend -m "New commit message"
git commit --amend --no-edit  # Keep same message, just add more changes
```

**When to use it:** When you forgot to include a file or made a typo in your commit message.

**How it works:** Stage the changes you want to add with `git add`, then run `git commit --amend`.

---

### View What Changed in a File

**What it does:** Shows you exactly what lines changed in a file.

```bash
git diff filename.txt         # Changes not yet staged
git diff --staged filename.txt # Changes that ARE staged
```

**When to use it:** When you want to review exactly what changed before committing.

---

### Revert a Commit (Safe Undo)

**What it does:** Creates a NEW commit that undoes the changes from a previous commit.

```bash
git revert commit-hash
```

**When to use it:** When you need to undo a commit that's already been pushed to remote. Unlike `reset`, this doesn't rewrite history.

**How to get commit hash:** Use `git log --oneline` to see commit hashes.

---

### Merge Conflicts (Oh Fuck)

**What they are:** When Git can't automatically merge changes because you and someone else edited the same lines.

**What to do:**

1. Git will mark the conflicts in your files with `<<<<<<<`, `=======`, and `>>>>>>>`.
2. Open the file and manually choose which changes to keep.
3. Remove the conflict markers.
4. Stage the resolved file with `git add`.
5. Commit the merge with `git commit`.

**When this happens:** Usually during `git pull` or `git merge` when multiple people edited the same code.

**Pro tip:** Don't panic. Just read the marked sections carefully and decide what stays.

---

## 5. Power Moves (Advanced But Useful)

Once you're comfortable with the basics, these commands will level you up.

### Stash Changes

**What it does:** Temporarily saves your uncommitted changes and gives you a clean working directory.

```bash
git stash                     # Stash current changes
git stash list                # See all stashes
git stash pop                 # Re-apply most recent stash and remove it
git stash apply               # Re-apply stash but keep it in stash list
```

**When to use it:** When you need to switch branches but have uncommitted changes you're not ready to commit yet.

---

### Cherry-Pick a Commit

**What it does:** Applies a specific commit from another branch onto your current branch.

```bash
git cherry-pick commit-hash
```

**When to use it:** When you want just ONE specific commit from another branch without merging everything.

---

### Rebase (Advanced)

**What it does:** Moves your branch's commits to start from a different point—makes history cleaner.

```bash
git rebase branch-name
```

**When to use it:** When you want a linear project history instead of messy merge commits.

**Warning:** Never rebase commits that have been pushed to shared branches. Only rebase local work.

---

### Show Commit Details

**What it does:** Shows you exactly what changed in a specific commit.

```bash
git show commit-hash
```

**When to use it:** When you need to see what a particular commit actually did.

---

### Tag a Commit (Version Marking)

**What it does:** Marks a specific commit with a version label (like `v1.0`).

```bash
git tag v1.0                  # Create tag
git tag                       # List all tags
git push origin --tags        # Push tags to remote
```

**When to use it:** When you're releasing a version or marking important milestones.

---

## 6. Quick Reference Cheat Sheet

| Command                     | What It Does                    |
| --------------------------- | ------------------------------- |
| `git status`                | Check what's changed            |
| `git add .`                 | Stage all changes               |
| `git commit -m "message"`   | Commit staged changes           |
| `git push`                  | Upload to remote                |
| `git pull`                  | Download from remote            |
| `git switch -c branch-name` | Create and switch to new branch |
| `git log --oneline`         | See commit history              |
| `git reset --soft HEAD~1`   | Undo last commit (keep changes) |
| `git restore filename.txt`  | Discard changes to file         |
| `git stash`                 | Temporarily save changes        |

---

## 7. Common Workflows

### Starting a New Feature

```bash
git switch -c feature-branch-name
# Make your changes
git add .
git commit -m "Add feature description"
git push -u origin feature-branch-name
```

### Daily Work Cycle

```bash
git pull                      # Get latest changes
# Make your changes
git status                    # Check what changed
git add .                     # Stage changes
git commit -m "Description"   # Commit
git push                      # Share with team
```

### Fixing a Mistake Before Pushing

```bash
git reset --soft HEAD~1       # Undo last commit
# Fix the issue
git add .                     # Stage again
git commit -m "Correct message"
git push
```

---

## 8. Pro Tips

1. **Commit often, push regularly** - Small commits are easier to understand and revert if needed.
2. **Write clear commit messages** - Your future self will thank you.
3. **Use branches for everything** - Keep main branch clean, do work in feature branches.
4. **Check status constantly** - `git status` is your friend. Use it liberally.
5. **Don't panic** - Almost everything in Git is recoverable. Take a breath, read the error, try again.

# GitHub Learning Guide - Step by Step

This guide will teach you GitHub concepts using this repository as a sandbox.

## 📚 Table of Contents

1. [Repository (Repo)](#1-repository-repo)
2. [Commits](#2-commits)
3. [Branches](#3-branches)
4. [Pull Requests (PRs)](#4-pull-requests-prs)
5. [Forks](#5-forks)
6. [Issues](#6-issues)
7. [Workflow Examples](#7-workflow-examples)

---

## 1. Repository (Repo)

**What is it?**
A repository (repo) is like a folder for your project that tracks all changes to your files over time.

**In your case:**
- **Local repo**: `/Users/evzenvasiljev/Documents/Waterbox/sf-hevy-gd`
- **Remote repo**: `git@github.com:evzenvasiljev/sf-hevy-gd.git` (on GitHub)

**Key concepts:**
- **Local**: On your computer
- **Remote**: On GitHub's servers
- **Clone**: Copy a remote repo to your computer
- **Push**: Send your local changes to the remote
- **Pull**: Get changes from remote to local

**Commands to explore:**
```bash
git remote -v          # See where your repo is connected
git status             # See what's changed locally
```

---

## 2. Commits

**What is it?**
A commit is a snapshot of your project at a specific point in time. Think of it as a "save point" with a message describing what changed.

**Commit structure:**
- **Hash**: Unique ID (e.g., `21570cd`)
- **Message**: Description of what changed
- **Author**: Who made the change
- **Date**: When it was made

**The 3 stages of a file:**
1. **Working Directory**: Files you're editing (untracked/modified)
2. **Staging Area**: Files ready to be committed (`git add`)
3. **Repository**: Files that are committed (`git commit`)

**Workflow:**
```
Edit file → git add → git commit → git push
```

**Commands:**
```bash
git add <file>         # Stage a file (prepare for commit)
git commit -m "msg"    # Create a commit with message
git log                # See commit history
git show <hash>        # See what changed in a commit
```

---

## 3. Branches

**What is it?**
A branch is an independent line of development. The default branch is usually `main` or `master`.

**Why use branches?**
- Work on features without breaking main code
- Experiment safely
- Collaborate without conflicts
- Review changes before merging

**Common branches:**
- `main`: Production-ready code
- `develop`: Development branch
- `feature/xxx`: New features
- `bugfix/xxx`: Bug fixes

**Commands:**
```bash
git branch                    # List branches
git branch <name>             # Create a branch
git checkout <name>           # Switch to branch
git checkout -b <name>        # Create and switch
git merge <branch>            # Merge branch into current
```

**Visual representation:**
```
main:     A---B---C
                \
feature:         D---E
```

---

## 4. Pull Requests (PRs)

**What is it?**
A Pull Request (PR) is a request to merge changes from one branch into another. It's how you:
- Review code before merging
- Discuss changes
- Get feedback
- Run automated tests

**PR Workflow:**
1. Create a branch
2. Make changes and commit
3. Push branch to GitHub
4. Open a PR on GitHub
5. Review and discuss
6. Merge (or close)

**When to use PRs:**
- Merging feature branches
- Contributing to open source
- Code review process
- Even for your own repos (good practice!)

---

## 5. Forks

**What is it?**
A fork is your own copy of someone else's repository. You can:
- Make changes without affecting the original
- Experiment freely
- Contribute back via PRs

**Fork vs Clone:**
- **Clone**: Copy to your computer (you have access)
- **Fork**: Copy to your GitHub account (you own it)

**Fork workflow:**
1. Fork a repo on GitHub
2. Clone your fork locally
3. Make changes
4. Push to your fork
5. Open PR to original repo

---

## 6. Issues

**What is it?**
Issues are like to-do items or bug reports for your project. They help:
- Track bugs
- Plan features
- Discuss ideas
- Organize work

**Issue lifecycle:**
- Open → In Progress → Closed
- Can link to PRs
- Can assign to people
- Can add labels

---

## 7. Workflow Examples

### Example 1: Making a Simple Change
```bash
# 1. Edit a file
nano README.md

# 2. See what changed
git status

# 3. Stage the change
git add README.md

# 4. Commit
git commit -m "Add DDLs section to README"

# 5. Push to GitHub
git push
```

### Example 2: Working with Branches
```bash
# 1. Create a feature branch
git checkout -b feature/add-ddl-scripts

# 2. Make changes
# ... edit files ...

# 3. Commit
git add .
git commit -m "Add DDL scripts"

# 4. Push branch
git push -u origin feature/add-ddl-scripts

# 5. On GitHub: Open a PR
# 6. After review, merge PR
# 7. Delete branch locally
git checkout main
git branch -d feature/add-ddl-scripts
```

### Example 3: Updating from Remote
```bash
# Get latest changes from GitHub
git pull origin main

# Or fetch first, then merge
git fetch origin
git merge origin/main
```

---

## 🎯 Practice Exercises

We'll do these together using your repo!

1. ✅ Make your first commit (you have uncommitted changes!)
2. Create a branch for a new feature
3. Make changes on that branch
4. Create a PR
5. Merge the PR
6. Create an issue
7. Link issue to PR

---

## 📖 Key Git Concepts Cheat Sheet

| Concept | Description | Command |
|---------|-------------|---------|
| **Repository** | Project folder with version control | `git init` |
| **Commit** | Snapshot of changes | `git commit` |
| **Branch** | Independent line of development | `git branch` |
| **Merge** | Combine branches | `git merge` |
| **Pull Request** | Request to merge changes | (GitHub UI) |
| **Fork** | Copy of someone's repo | (GitHub UI) |
| **Clone** | Copy repo to your computer | `git clone` |
| **Push** | Send commits to remote | `git push` |
| **Pull** | Get commits from remote | `git pull` |
| **Staging** | Prepare files for commit | `git add` |

---

## 🔍 Useful Commands for Learning

```bash
# See what's changed
git status
git diff

# See history
git log --oneline --graph --all
git log --oneline -10

# See a specific commit
git show <hash>

# See branch structure
git log --graph --oneline --all

# Undo changes (be careful!)
git restore <file>           # Discard uncommitted changes
git reset --soft HEAD~1      # Undo last commit, keep changes
```

---

Ready to start? Let's begin with Exercise 1!


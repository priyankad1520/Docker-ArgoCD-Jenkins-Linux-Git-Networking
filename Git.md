# Git and GitHub

## 1. What is Git?
A tool that remembers every change made in your project.
Git is a **Distributed Version Control System (DVCS)** used to track changes in files and source code over time.

It helps developers:

* Track code changes
* Work together in teams
* Manage different versions of a project
* Restore previous versions if needed

#### Why Git is Used

* Tracks changes in code/files
* Allows multiple developers to work together
* Maintains project history
* Helps recover deleted or old code
* Supports branching and merging
* Used in DevOps and CI/CD workflows

#### Features of Git

| Feature         | Explanation                        |
| --------------- | ---------------------------------- |
| Version Control | Tracks file changes                |
| Distributed     | Every developer has a copy of repo |
| Fast            | Lightweight and efficient          |
| Branching       | Create separate work environments  |
| Collaboration   | Multiple people can work together  |
| Rollback        | Return to previous versions        |

---

## 2. What is GitHub?
Website where Git repositories are stored and shared. GitHub is a **cloud-based platform** used to store Git repositories online.

It provides:

* Online code storage
* Team collaboration
* Pull requests
* Code review
* CI/CD integration

#### Why GitHub is Used

* Store code online
* Backup repositories
* Share code with teams
* Collaboration platform
* Used by companies for projects
* Integrates with CI/CD tools

## Git vs GitHub

| Git                 | GitHub                  |
| ------------------- | ----------------------- |
| Tool                | Cloud Platform          |
| Works locally       | Works on cloud          |
| Tracks versions     | Hosts repositories      |
| Installed on system | Access through internet |
| Command line tool   | Website/platform        |

---

### 3. Repository (Repo)
A repository is a folder that contains: Project files, Git history, Branch information, Commit history
- Types of Repository:
- Local Repository: Stored on your computer.
- Remote Repository: Stored on GitHub or cloud platforms.

## 4. Branch
A branch is a separate line of development.
- It allows developers to work on: New features, Bug fixes, Experiments. without affecting the main code.
#### Why Branches are Used

* Parallel development
* Team collaboration
* Safe experimentation
* Organized workflow
* Prevent breaking main code

# Types of Branches

## 1. Main Branch (main/master)
The primary branch of the project.
- Contains: Stable code, Production-ready application, Final version of project
- Example: `main`

## 2. Feature Branch
Used to develop new features.

## Workflow

```text
main → create feature branch → develop → test → merge into main
```

## Example

```bash
feature/login-page
```

---

# Release Branch

Used when preparing a new release version.

## Purpose

* Final testing
* Bug fixes
* Documentation updates
* Version preparation

## Advantage

Development can continue on other branches while release preparation happens.

---

# Hotfix Branch

Used to fix urgent production issues.

## Workflow

```text
main → hotfix branch → fix issue → merge back → deploy immediately
```

## Characteristics

* High priority
* Quick fix
* Minimal changes
* Immediate deployment

---

# Example of Branches in E-Commerce Application

| Branch         | Purpose                      |
| -------------- | ---------------------------- |
| main           | Live website code            |
| feature branch | New product filter feature   |
| release branch | Preparing Version 2.0        |
| hotfix branch  | Fix payment failure urgently |

---

# 5. Commit

A commit is a saved snapshot of your project at a specific time.

It records:

* File changes
* Author information
* Date and time
* Commit message
* Unique commit ID (hash)

---

# Why Commit is Important

* Tracks project history
* Helps undo mistakes
* Maintains version history
* Allows collaboration

---

# Real-Life Example

Commit is like taking a photo of your project.

You can return to any old photo/version anytime.

---

# Commit Workflow

```text
Working Directory → Staging Area → Commit → Repository
```

---

# Steps to Create a Commit

## Step 1: Edit Files

Modify project files.

---

## Step 2: Add to Staging Area

```bash
git add filename
```

Add all files:

```bash
git add .
```

---

## Step 3: Commit Changes

```bash
git commit -m "Added login feature"
```

### Here:

* `-m` means message

---

# View Commit History

```bash
git log --oneline
```

---

# 6. Staging Area

The staging area is an intermediate area where selected changes are prepared before commit.

## Simple Meaning

Staging = Telling Git:

> “Include this file in the next commit.”

---

# Important Point

If you modify a file again after staging,
the new changes are NOT included unless you stage again.

---

# Staging Commands

## Add One File

```bash
git add filename
```

---

## Add All Files

```bash
git add .
```

---

## Check Status

```bash
git status
```

### Output Types

| Status   | Meaning          |
| -------- | ---------------- |
| Staged   | Ready for commit |
| Unstaged | Not selected yet |

---

## Remove File from Staging

```bash
git restore --staged filename
```

---

# 7. .git Folder

The `.git` folder is the hidden brain/database of Git repository.

It stores:

* Commit history
* Branch details
* Configuration settings
* Staging information
* Repository metadata

---

# When is .git Created?

When you run:

```bash
git init
```

---

# Why It Starts with Dot (.)

Files starting with `.` are hidden files in Linux/Unix systems.

---

# What .git Contains

| Content        | Purpose             |
| -------------- | ------------------- |
| Commit History | Stores all commits  |
| Branch Info    | Branch references   |
| Config Files   | Repository settings |
| Objects        | Snapshots of files  |
| Staging Data   | Prepared changes    |

---

# See Hidden .git Folder

## Linux Command

```bash
ls -a
```

---

# 8. Fork

Fork means creating your own copy of someone else's repository on GitHub.

## Why Fork is Used

* Contribute to open-source projects
* Make changes independently
* Experiment safely

---

# 9. Clone

Clone means downloading a repository from GitHub to your local system.

## Command

```bash
git clone <repository-url>
```

Example:

```bash
git clone https://github.com/user/project.git
```

---

# 10. Pull Request (PR)

A Pull Request is a request to merge your code into another branch.

## Workflow

```text
Create Branch → Make Changes → Push Code → Create PR → Review → Merge
```

---

# Why Pull Request is Important

* Code review
* Team collaboration
* CI/CD trigger
* Quality checking

---

# 11. Git Workflow in Real Project

## Feature Development Workflow

```text
1. Clone Repository
2. Create Feature Branch
3. Make Changes
4. git add .
5. git commit -m "message"
6. git push
7. Create Pull Request
8. Code Review
9. Merge into Main
10. CI/CD Pipeline Triggered
```

---

# Common Git Commands

| Command      | Purpose                 |
| ------------ | ----------------------- |
| git init     | Initialize repository   |
| git clone    | Download repository     |
| git status   | Check file status       |
| git add      | Add files to staging    |
| git commit   | Save snapshot           |
| git log      | View history            |
| git branch   | View branches           |
| git checkout | Switch branch           |
| git merge    | Merge branches          |
| git pull     | Download latest changes |
| git push     | Upload changes          |
| git restore  | Restore changes         |

---

# Important Interview Questions

## What is Git?

Git is a distributed version control system used to track code changes.

---

## Difference Between Git and GitHub?

Git is a version control tool.
GitHub is a cloud platform for hosting Git repositories.

---

## What is Commit?

A commit is a saved snapshot of project changes.

---

## What is Staging Area?

Temporary area where changes are prepared before commit.

---

## What is Branch?

A separate line of development.

---

## What is Pull Request?

A request to merge code into another branch.

---

# Simple Real-Time Workflow Example

```text
Developer creates feature branch
        ↓
Writes code
        ↓
git add .
        ↓
git commit -m "Added feature"
        ↓
git push
        ↓
Create Pull Request
        ↓
Code Review
        ↓
Merge to main
        ↓
CI/CD Pipeline Triggered
        ↓
Deployment
```

---

# Summary

| Topic        | Meaning                   |
| ------------ | ------------------------- |
| Git          | Version control tool      |
| GitHub       | Cloud platform for Git    |
| Repository   | Project storage           |
| Branch       | Separate development line |
| Commit       | Saved snapshot            |
| Staging      | Prepare files for commit  |
| Pull Request | Request to merge code     |
| Fork         | Copy repository           |
| Clone        | Download repository       |
| .git         | Hidden Git database       |

# Basic Git Commands Guide

Git is a version control system that tracks changes to files in your projects. 
#### 1. **git init** - `git init`.  
Initialize a Repository. Creates a new Git repository in your current directory.

**Example:**
```bash
$ cd my-project
$ git init
Initialized empty Git repository in /path/to/my-project/.git/
This creates a `.git` folder that stores all version history and configuration.
```
---
#### 2. **git clone** - `git clone <repository-url>`.  
Copy a Repository. Downloads an entire repository from a remote source (like GitHub) to your local machine.

**Example:**
```bash
$ git clone https://github.com/priyankad1520/terraform-zero-to-hero.git
This is commonly used when starting work on an existing project.
```
---

#### 3. **git status** -  `git status`.
Check Repository Status. Shows which files have been modified, added, or are untracked.

**Example:**
```bash
$ git status
Output: nothing added to commit but untracked changes present (working directory)
```

---

#### 4. **git add** - Stage Changes
Prepares modified or new files to be committed. You're telling Git "I want to include these changes in my next commit."

```bash
git add <file>           # Add specific file
git add .               # Add all changes
git add *.tf            # Add files matching a pattern
```

**Example:**
```bash
$ git add main.tf variables.tf
$ git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   main.tf
        modified:   variables.tf
```
---
#### 5. **git commit** - `git commit -m "Your commit message"`.
Save Changes. Records the staged changes to your repository with a descriptive message.

**Example:**
```bash
$ git commit -m "Add Terraform configuration for VPC setup"
[main a1b2c3d] Add Terraform configuration for VPC setup
 2 files changed, 45 insertions(+), 10 deletions(-)
```

**Best practices for commit messages:**
- Be descriptive and concise
- Use present tense: "Add feature" not "Added feature"
- Reference issue numbers: "Fix bug in #123"

---

#### 6. **git push** - Upload Changes to Remote
Sends your committed changes from your local repository to a remote server (like GitHub).

```bash
git push <remote> <branch>
Example: $ git push origin main
git push                 # Uses default remote (usually 'origin') and current branch
```
---
#### 7. **git pull** - Download Changes from Remote
Fetches changes from the remote repository and merges them into your local branch.

```bash
git pull <remote> <branch>
Example: $ git pull origin main
git pull                 # Uses default remote and current branch
```
---
#### Complete Workflow Example

```bash
# 1. Clone a repository
git clone https://github.com/priyankad1520/terraform-zero-to-hero.git
cd terraform-zero-to-hero

# 2. Check the current status
git status

# 3. Make changes to files (using your editor)
# ... edit main.tf ...

# 4. Stage the changes
git add main.tf

# 5. Check status again
git status

# 6. Commit the changes
git commit -m "Update VPC configuration with new subnet"

# 7. Pull latest changes from remote (good practice before pushing)
git pull origin main

# 8. Push your changes to remote
git push origin main
```

# Advanced Git Commands Guide

#### 1. **git branch** - Manage Branches
Creates, lists, and deletes branches to work on features independently.

```bash
git branch                          # List local branches
git branch -a                       # List all branches (local + remote)
git branch <branch-name>            # Create a new branch: $ git branch feature/new-security-group
git branch -d <branch-name>         # Delete a branch
git branch -D <branch-name>         # Force delete a branch
git branch -m <old-name> <new-name> # Rename a branch
```
**Why use branches?**
- Work on features without affecting the main codebase
- Allow multiple developers to work simultaneously
- Keep experimental code separate

---

#### 2. **git checkout** - Switch Branches or Restore Files
Switches between branches or restores files to a previous state.

```bash
git checkout <branch-name>           # Switch to a branch 'main': $ git checkout main
git checkout -b <new-branch-name>    # Create and switch to a new branch 'feature/logging': $ git checkout -b feature/logging
git checkout <commit-hash> -- <file> # Restore file (config.tf) from specific commit: $ git checkout develop -- config.tf
```
**Common use case:**
```bash
# Start a new feature
$ git checkout -b feature/add-monitoring
# Make changes
# ... edit files ...
# Stage and commit
$ git add .
$ git commit -m "Add CloudWatch monitoring"
# Switch back to main
$ git checkout main
```
---
#### 3. **git merge** - Combine Branches
Integrates changes from one branch into another (typically merging features into main).

```bash
git merge <branch-name>              # Merge specified branch into current branch
git merge --no-ff <branch-name>      # Merge with merge commit (preserves history)
```

**Example:**
```bash
$ git checkout main
Switched to branch 'main'

$ git merge feature/logging
Updating a1b2c3d..f7e6d5c
Fast-forward
 logging.tf | 25 +++++++++++++++++++++++++
 1 file changed, 25 insertions(+)
```

**Merge with commit history preserved:**
```bash
$ git merge --no-ff feature/logging
Merge made by the 'recursive' strategy.
 logging.tf | 25 +++++++++++++++++++++++++
 1 file changed, 25 insertions(+)
```

**Handling merge conflicts:**
When Git can't automatically merge, you'll get a conflict:
```bash
$ git merge feature/network
Auto-merging main.tf
CONFLICT (content): Merge conflict in main.tf
Automatic merge failed; fix conflicts and then commit the result.
```

Edit the conflicted file to resolve manually, then:
```bash
$ git add main.tf
$ git commit -m "Resolve merge conflict in main.tf"
```

---

#### 4. **git rebase** - Rewrite Commit History
Re-applies your commits on top of another branch, creating a linear history.

```bash
git rebase <branch-name>             # Rebase current branch onto another
git rebase -i HEAD~<number>          # Interactive rebase last N commits
git rebase --continue                # Resume after fixing conflicts
git rebase --abort                   # Cancel rebase
```

**Example:**
```bash
$ git checkout feature/security
$ git rebase main
First, rewinding head to replay your work on top of it...
Applying: Add security groups
Applying: Add IAM policies
```

**Interactive rebase (squash commits):**
```bash
$ git rebase -i HEAD~3
# Opens editor with last 3 commits:
# pick a1b2c3d Add security groups
# pick f7e6d5c Fix security group rules
# pick 9k8j7l6 Update documentation

# Change to:
# pick a1b2c3d Add security groups
# squash f7e6d5c Fix security group rules
# squash 9k8j7l6 Update documentation

# Result: combines all 3 commits into 1
```

**Merge vs Rebase:**
- **Merge**: Preserves complete history, creates merge commits
- **Rebase**: Creates linear history, cleaner but rewrites history

---

#### 5. **git reset** - Undo Changes
Moves the HEAD pointer to a previous commit, undoing changes.

**⚠️ Warning:** `git reset --hard` permanently deletes changes!
```bash
git reset --soft <commit>            # Undo commit, keep changes staged
git reset --mixed <commit>           # Undo commit, keep changes unstaged (default)
git reset --hard <commit>            # Undo commit and discard all changes
After reset check the git status
```
---

#### 6. **git revert** - Create Undo Commit (Safe Alternative)
Creates a new commit that reverses changes from a previous commit (safer than reset).

```bash
git revert <commit-hash>             # Create commit that undoes changes
git revert -n <commit-hash>          # Revert without committing
```

**Example:**
```bash
$ git log --oneline
f7e6d5c Update documentation
a1b2c3d Add security groups
9k8j7l6 Initial setup

$ git revert a1b2c3d
# Opens editor for commit message
[main 3x2y1z0] Revert "Add security groups"
 1 file changed, 10 deletions(-)

$ git log --oneline
3x2y1z0 Revert "Add security groups"
f7e6d5c Update documentation
a1b2c3d Add security groups
```

**Merge vs Reset vs Revert:**
- **Reset**: Rewrites history (use locally only)
- **Revert**: Creates new commit undoing changes (safe, use for shared branches)
- **Merge**: Combines branches

---

#### 7. **git log** - View Commit History
Displays detailed commit history with various filtering options.

```bash
git log                              # Show all commits
git log --oneline                    # Compact format
git log -n 5                         # Show last 5 commits
git log --graph --all --decorate     # Visual branch graph
git log --author="name"              # Commits by author
git log -p                           # Show changes in each commit
git log -p -n 1                      # Shows full diff of most recent commit
git log --since="2 weeks ago"        # Commits in timeframe
```
---

#### 8. **git stash** - Temporarily Save Changes
Saves uncommitted changes without committing, useful when switching branches.

```bash
git stash                            # Stash current changes
git stash list                       # List all stashes
git stash pop                        # Apply and remove latest stash
git stash apply                      # Apply stash without removing
git stash drop                       # Delete a stash
```

**Example:**
```bash
# You're working on a feature but need to switch branches
$ git status
Changes not staged for commit:
  modified:   main.tf

$ git stash
Saved working directory and index state WIP on main: f7e6d5c Update documentation

$ git checkout hotfix-branch
# ... fix the bug ...

$ git checkout main
$ git stash list
stash@{0}: WIP on main: f7e6d5c Update documentation

$ git stash pop
On branch main
Changes not staged for commit:
  modified:   main.tf
```

---

#### 9. **git tag** - Mark Important Commits
Creates named references to specific commits (typically for releases).

```bash
git tag <tag-name>                   # Create lightweight tag: $ git tag v1.0.0
git tag -a <tag-name> -m "message"   # Create annotated tag: $ git tag -a v1.0.1 -m "Release version 1.0.1"
git tag -l                           # List all tags
git push origin <tag-name>           # Push specific tag: $ git push origin v1.0.1
git push origin --tags               # Push all tags
$ git log --oneline --all
f7e6d5c (tag: v1.0.1, HEAD -> main) Update documentation
a1b2c3d (tag: v1.0.0) Add security groups
```
---

#### 10. **git cherry-pick** - Apply Specific Commits
Applies a specific commit from one branch to another.

```bash
git cherry-pick <commit-hash>        # Apply commit to current branch
git cherry-pick <hash1> <hash2>      # Apply multiple commits
git cherry-pick --continue           # Resume after resolving conflicts
```

**Example:**
```bash
# You need a specific bug fix from another branch
$ git log --oneline develop
a1b2c3d Fix critical bug in parsing

$ git checkout main
$ git cherry-pick a1b2c3d
[main f7e6d5c] Fix critical bug in parsing
 1 file changed, 5 insertions(+)
```
---

#### 11. **git diff** - View Changes
Shows differences between commits, branches, or working directory.

```bash
git diff                             # Changes in working directory
git diff --staged                    # Changes staged for commit
git diff <branch1> <branch2>         # Differences between branches
git diff <commit1> <commit2>         # Differences between commits
git diff <commit> -- <file>          # Changes to specific file
Example: $ git diff main..feature/vpc
# Shows all differences between main and feature/vpc branches
```
---
#### 12. **git reflog** - Recover Lost Commits
Shows history of HEAD changes; useful for recovering accidentally deleted commits.

```bash
git reflog                           # Show reference logs
git show <reflog-entry>              # Show commit details
git reset --hard <reflog-entry>      # Restore to reflog entry
```
---

#### Advanced Workflow Example

```bash
# 1. Create and switch to a feature branch
$ git checkout -b feature/monitoring

# 2. Make multiple commits
$ git add metrics.tf
$ git commit -m "Add CloudWatch metrics"
$ git add alarms.tf
$ git commit -m "Add CloudWatch alarms"
$ git add dashboard.tf
$ git commit -m "Add CloudWatch dashboard"

# 3. Clean up commits using interactive rebase
$ git rebase -i HEAD~3
# Squash the 3 commits into 1

# 4. Switch to main and pull latest
$ git checkout main
$ git pull origin main

# 5. Merge feature into main
$ git merge --no-ff feature/monitoring

# 6. Create a release tag
$ git tag -a v2.0.0 -m "Release monitoring features"

# 7. Push everything
$ git push origin main
$ git push origin --tags

# 8. Clean up feature branch
$ git branch -d feature/monitoring
$ git push origin --delete feature/monitoring
```

---

## Quick Reference Table

| Command      | Purpose |
|--------------|---------|
| `git init`   | Initialize a new repository |
| `git clone`  | Copy a remote repository locally |
| `git status` | View current repository status |
| `git add`    | Stage files for commit |
| `git commit -m "message"` | Save staged changes |
| `git push`   | Upload commits to remote |
| `git pull`   | Download and merge remote changes |
| `git branch` | List, create, delete branches |
| `git checkout` | Switch branches or restore files |
| `git merge`   | Combine branches |
| `git rebase`  | Rewrite history, create linear commits |
| `git reset`   | Undo commits (local only) |
| `git revert`  | Create undo commit (shared branches) |
| `git log`     | View commit history |
| `git stash`   | Temporarily save changes |
| `git tag`     | Mark important commits |
| `git cherry-pick` | Apply specific commits |
| `git diff`    | View changes |
| `git reflog`  | Recover lost commits |


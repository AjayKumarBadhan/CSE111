# Complete Git and GitHub Tutorial

## Table of Contents
1. [Introduction](#introduction)
2. [Git Basics](#git-basics)
3. [Essential Git Commands](#essential-git-commands)
4. [Branching and Merging](#branching-and-merging)
5. [Remote Repositories](#remote-repositories)
6. [GitHub Specific Commands](#github-specific-commands)
7. [Advanced Git Operations](#advanced-git-operations)
8. [Troubleshooting and Recovery](#troubleshooting-and-recovery)

## Introduction

**Git** is a distributed version control system that tracks changes in files and coordinates work among multiple developers. **GitHub** is a web-based hosting service for Git repositories that provides additional collaboration features.

### Prerequisites
- Git installed on your system
- GitHub account (for GitHub-specific operations)
- Basic command line knowledge

---

## Git Basics

### What is Git?
Git is a version control system that helps you track changes to your code over time. It allows multiple developers to work on the same project without conflicts and maintains a complete history of all changes.

### Key Concepts
- **Repository (Repo)**: A directory containing your project files and Git metadata
- **Commit**: A snapshot of your project at a specific point in time
- **Branch**: A parallel version of your repository
- **Working Directory**: Your local project folder
- **Staging Area**: A preparation area for commits
- **Remote**: A version of your repository hosted elsewhere (like GitHub)

---

## Essential Git Commands

### 1. Repository Initialization and Configuration

#### `git init`
**Definition**: Initializes a new Git repository in the current directory.

**Explanation**: Creates a `.git` folder that contains all the metadata and version history for your project.

**Syntax**:
```bash
git init [directory-name]
```

**Examples**:
```bash
# Initialize repository in current directory
git init

# Initialize repository in a new directory
git init my-project
```

#### `git config`
**Definition**: Sets configuration options for Git.

**Explanation**: Configures user information, preferences, and Git behavior. Can be set globally or per repository.

**Syntax**:
```bash
git config [--global|--local] <key> <value>
```

**Examples**:
```bash
# Set global username and email
git config --global user.name "John Doe"
git config --global user.email "john@example.com"

# Set default branch name
git config --global init.defaultBranch main

# View all configurations
git config --list
```

### 2. Basic File Operations

#### `git add`
**Definition**: Adds changes from the working directory to the staging area.

**Explanation**: Prepares files for the next commit. Files must be staged before they can be committed.

**Syntax**:
```bash
git add <file>
git add <directory>
git add .
```

**Examples**:
```bash
# Add specific file
git add index.html

# Add all files in directory
git add src/

# Add all changes
git add .

# Add all files with specific extension
git add *.js
```

#### `git commit`
**Definition**: Creates a snapshot of the staged changes.

**Explanation**: Permanently saves the staged changes to the repository history with a descriptive message.

**Syntax**:
```bash
git commit -m "commit message"
git commit -am "commit message"
```

**Examples**:
```bash
# Commit staged changes with message
git commit -m "Add login functionality"

# Stage and commit all tracked files
git commit -am "Fix navigation bug"

# Commit with detailed message
git commit -m "feat: implement user authentication

- Add login form validation
- Integrate with OAuth provider
- Update user session management"
```

#### `git status`
**Definition**: Shows the current state of the working directory and staging area.

**Explanation**: Displays which files are modified, staged, or untracked.

**Syntax**:
```bash
git status
git status --short
```

**Examples**:
```bash
# Full status information
git status

# Condensed status output
git status -s
```

#### `git log`
**Definition**: Displays the commit history.

**Explanation**: Shows a chronological list of commits with details like author, date, and commit message.

**Syntax**:
```bash
git log [options]
```

**Examples**:
```bash
# Basic log
git log

# One line per commit
git log --oneline

# Show last 5 commits
git log -5

# Show commits with file changes
git log --stat

# Graphical representation
git log --graph --oneline --all
```

#### `git diff`
**Definition**: Shows differences between various states of files.

**Explanation**: Compares changes between working directory, staging area, and committed versions.

**Syntax**:
```bash
git diff [options] [commit] [file]
```

**Examples**:
```bash
# Show unstaged changes
git diff

# Show staged changes
git diff --staged

# Compare two commits
git diff HEAD~1 HEAD

# Show changes in specific file
git diff index.html
```

---

## Branching and Merging

### Branch Management

#### `git branch`
**Definition**: Lists, creates, or deletes branches.

**Explanation**: Branches allow you to work on different features or experiments in isolation.

**Syntax**:
```bash
git branch [branch-name]
git branch -d [branch-name]
git branch -D [branch-name]
```

**Examples**:
```bash
# List all branches
git branch

# Create new branch
git branch feature-login

# Delete merged branch
git branch -d feature-login

# Force delete branch
git branch -D experimental-feature

# List remote branches
git branch -r
```

#### `git checkout`
**Definition**: Switches between branches or restores files.

**Explanation**: Changes your working directory to match the specified branch or commit.

**Syntax**:
```bash
git checkout [branch-name]
git checkout -b [new-branch-name]
```

**Examples**:
```bash
# Switch to existing branch
git checkout main

# Create and switch to new branch
git checkout -b feature-payment

# Restore file from last commit
git checkout -- index.html

# Switch to specific commit
git checkout a1b2c3d
```

#### `git switch` (Git 2.23+)
**Definition**: Modern command for switching branches.

**Explanation**: Cleaner alternative to `git checkout` for branch operations.

**Syntax**:
```bash
git switch [branch-name]
git switch -c [new-branch-name]
```

**Examples**:
```bash
# Switch to branch
git switch main

# Create and switch to new branch
git switch -c feature-dashboard

# Switch to previous branch
git switch -
```

#### `git merge`
**Definition**: Combines changes from different branches.

**Explanation**: Integrates commits from one branch into another, typically merging feature branches into main.

**Syntax**:
```bash
git merge [branch-name]
git merge --no-ff [branch-name]
```

**Examples**:
```bash
# Merge feature branch into current branch
git merge feature-login

# Merge without fast-forward
git merge --no-ff feature-payment

# Abort merge in case of conflicts
git merge --abort
```

---

## Remote Repositories

### Remote Management

#### `git remote`
**Definition**: Manages remote repository connections.

**Explanation**: Handles the URLs and names of remote repositories you can push to or pull from.

**Syntax**:
```bash
git remote [add|remove|rename] [name] [url]
```

**Examples**:
```bash
# List remotes
git remote -v

# Add remote repository
git remote add origin https://github.com/username/repository.git

# Remove remote
git remote remove origin

# Rename remote
git remote rename origin upstream
```

#### `git clone`
**Definition**: Creates a local copy of a remote repository.

**Explanation**: Downloads the entire repository history and sets up remote tracking.

**Syntax**:
```bash
git clone [url] [directory-name]
```

**Examples**:
```bash
# Clone repository
git clone https://github.com/username/project.git

# Clone to specific directory
git clone https://github.com/username/project.git my-project

# Clone specific branch
git clone -b develop https://github.com/username/project.git

# Shallow clone (recent history only)
git clone --depth 1 https://github.com/username/project.git
```

#### `git fetch`
**Definition**: Downloads changes from remote repository without merging.

**Explanation**: Updates your local repository with remote changes but doesn't modify your working directory.

**Syntax**:
```bash
git fetch [remote] [branch]
```

**Examples**:
```bash
# Fetch from default remote
git fetch

# Fetch from specific remote
git fetch origin

# Fetch specific branch
git fetch origin main

# Fetch all remotes
git fetch --all
```

#### `git pull`
**Definition**: Fetches and merges changes from remote repository.

**Explanation**: Combines `git fetch` and `git merge` to update your current branch with remote changes.

**Syntax**:
```bash
git pull [remote] [branch]
```

**Examples**:
```bash
# Pull from default remote and branch
git pull

# Pull from specific remote and branch
git pull origin main

# Pull with rebase instead of merge
git pull --rebase

# Pull specific branch
git pull origin feature-branch
```

#### `git push`
**Definition**: Uploads local commits to remote repository.

**Explanation**: Sends your committed changes to the remote repository for others to access.

**Syntax**:
```bash
git push [remote] [branch]
```

**Examples**:
```bash
# Push to default remote and branch
git push

# Push to specific remote and branch
git push origin main

# Push new branch to remote
git push -u origin feature-login

# Force push (use with caution)
git push --force

# Push all branches
git push --all origin

# Push tags
git push --tags
```

---

## GitHub Specific Commands

### GitHub CLI (gh) Commands

First, install GitHub CLI and authenticate:
```bash
# Install gh (varies by system)
# macOS: brew install gh
# Windows: winget install GitHub.cli

# Authenticate with GitHub
gh auth login
```

#### Repository Management

##### `gh repo create`
**Definition**: Creates a new repository on GitHub.

**Explanation**: Initializes a new repository both locally and on GitHub.

**Syntax**:
```bash
gh repo create [name] [flags]
```

**Examples**:
```bash
# Create public repository
gh repo create my-project --public

# Create private repository with description
gh repo create my-app --private --description "My awesome application"

# Create repository from current directory
gh repo create --source=. --public

# Create repository with README and license
gh repo create my-project --public --add-readme --license mit
```

##### `gh repo clone`
**Definition**: Clones a GitHub repository.

**Explanation**: Downloads a repository using GitHub CLI with enhanced features.

**Syntax**:
```bash
gh repo clone [repository]
```

**Examples**:
```bash
# Clone your repository
gh repo clone my-project

# Clone someone else's repository
gh repo clone username/repository

# Clone to specific directory
gh repo clone username/repository ./my-folder
```

#### Pull Requests

##### `gh pr create`
**Definition**: Creates a pull request on GitHub.

**Explanation**: Opens a pull request from your current branch to the target branch.

**Syntax**:
```bash
gh pr create [flags]
```

**Examples**:
```bash
# Create PR with interactive prompts
gh pr create

# Create PR with title and body
gh pr create --title "Add user authentication" --body "Implements login and signup functionality"

# Create draft PR
gh pr create --draft --title "WIP: Payment integration"

# Create PR to specific branch
gh pr create --base develop --title "Feature update"
```

##### `gh pr list`
**Definition**: Lists pull requests in the repository.

**Explanation**: Shows open, closed, or merged pull requests with filtering options.

**Syntax**:
```bash
gh pr list [flags]
```

**Examples**:
```bash
# List open PRs
gh pr list

# List all PRs
gh pr list --state all

# List PRs by author
gh pr list --author username

# List PRs with specific label
gh pr list --label bug
```

##### `gh pr checkout`
**Definition**: Checks out a pull request branch locally.

**Explanation**: Switches to the branch of a specific pull request for testing or review.

**Syntax**:
```bash
gh pr checkout [number]
```

**Examples**:
```bash
# Checkout PR #123
gh pr checkout 123

# Checkout PR by URL
gh pr checkout https://github.com/owner/repo/pull/123
```

#### Issues

##### `gh issue create`
**Definition**: Creates a new issue on GitHub.

**Explanation**: Opens a new issue with title, description, and labels.

**Syntax**:
```bash
gh issue create [flags]
```

**Examples**:
```bash
# Create issue with interactive prompts
gh issue create

# Create issue with title and body
gh issue create --title "Bug in login form" --body "Users cannot submit login credentials"

# Create issue with labels and assignee
gh issue create --title "Feature request" --label enhancement --assignee username
```

##### `gh issue list`
**Definition**: Lists issues in the repository.

**Explanation**: Shows repository issues with filtering and search capabilities.

**Syntax**:
```bash
gh issue list [flags]
```

**Examples**:
```bash
# List open issues
gh issue list

# List all issues
gh issue list --state all

# List issues assigned to you
gh issue list --assignee @me

# List issues with specific label
gh issue list --label bug
```

---

## Advanced Git Operations

### Rewriting History

#### `git rebase`
**Definition**: Reapplies commits on top of another base commit.

**Explanation**: Creates a linear project history by moving or combining commits.

**Syntax**:
```bash
git rebase [base-branch]
git rebase -i [commit]
```

**Examples**:
```bash
# Rebase current branch onto main
git rebase main

# Interactive rebase for last 3 commits
git rebase -i HEAD~3

# Continue rebase after resolving conflicts
git rebase --continue

# Abort rebase
git rebase --abort
```

#### `git reset`
**Definition**: Moves the current branch pointer to a specific commit.

**Explanation**: Unstages changes or moves branch history. Use with caution as it can lose work.

**Syntax**:
```bash
git reset [--soft|--mixed|--hard] [commit]
```

**Examples**:
```bash
# Unstage all files (soft reset)
git reset HEAD

# Reset to previous commit, keep changes
git reset --soft HEAD~1

# Reset to previous commit, unstage changes
git reset --mixed HEAD~1

# Reset to previous commit, discard changes
git reset --hard HEAD~1
```

#### `git revert`
**Definition**: Creates a new commit that undoes changes from a previous commit.

**Explanation**: Safely undoes changes without rewriting history.

**Syntax**:
```bash
git revert [commit]
```

**Examples**:
```bash
# Revert last commit
git revert HEAD

# Revert specific commit
git revert a1b2c3d

# Revert without creating commit
git revert --no-commit HEAD
```

### Stashing Changes

#### `git stash`
**Definition**: Temporarily saves uncommitted changes.

**Explanation**: Stores work-in-progress changes so you can switch branches or pull updates.

**Syntax**:
```bash
git stash [push|pop|list|drop]
```

**Examples**:
```bash
# Stash current changes
git stash

# Stash with message
git stash push -m "WIP: updating styles"

# List all stashes
git stash list

# Apply most recent stash
git stash pop

# Apply specific stash
git stash apply stash@{1}

# Drop stash
git stash drop stash@{0}
```

### Tags

#### `git tag`
**Definition**: Creates, lists, or deletes tags.

**Explanation**: Marks specific commits as releases or important milestones.

**Syntax**:
```bash
git tag [tag-name] [commit]
```

**Examples**:
```bash
# List all tags
git tag

# Create lightweight tag
git tag v1.0.0

# Create annotated tag
git tag -a v1.0.0 -m "Release version 1.0.0"

# Tag specific commit
git tag v0.9.0 a1b2c3d

# Delete tag
git tag -d v1.0.0

# Push tags to remote
git push --tags
```

---

## Troubleshooting and Recovery

### Common Issues and Solutions

#### Merge Conflicts
**Definition**: Occurs when Git cannot automatically merge changes.

**Resolution Steps**:
```bash
# 1. Identify conflicted files
git status

# 2. Edit files to resolve conflicts
# Look for conflict markers: <<<<<<<, =======, >>>>>>>

# 3. Stage resolved files
git add conflicted-file.txt

# 4. Complete the merge
git commit
```

#### Undoing Changes

##### `git checkout -- <file>`
**Definition**: Discards changes in working directory.

**Examples**:
```bash
# Discard changes in specific file
git checkout -- index.html

# Discard all changes
git checkout -- .
```

##### `git clean`
**Definition**: Removes untracked files from working directory.

**Examples**:
```bash
# Preview what will be deleted
git clean -n

# Remove untracked files
git clean -f

# Remove untracked files and directories
git clean -fd
```

#### Recovering Lost Commits

##### `git reflog`
**Definition**: Shows reference log of HEAD movements.

**Explanation**: Helps recover lost commits from resets or other operations.

**Examples**:
```bash
# Show reflog
git reflog

# Recover lost commit
git checkout HEAD@{2}
git branch recovery-branch

# Reset to previous state
git reset --hard HEAD@{1}
```

### Best Practices

1. **Commit Often**: Make small, focused commits with clear messages
2. **Use Branches**: Keep main branch stable, work on features in separate branches
3. **Pull Before Push**: Always pull latest changes before pushing
4. **Write Good Commit Messages**: Use present tense, be descriptive
5. **Review Before Committing**: Use `git diff` and `git status` to verify changes
6. **Backup Important Work**: Push regularly to remote repositories
7. **Use .gitignore**: Exclude files that shouldn't be tracked

### Useful Git Aliases

Add these to your `.gitconfig` file:
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.lg "log --oneline --graph --all"
git config --global alias.unstage "reset HEAD --"
```

---

## Conclusion

This tutorial covers the essential Git and GitHub commands you need for version control and collaboration. Practice these commands regularly, and remember that Git has excellent documentation available through `git help <command>` for any specific command you want to learn more about.

For GitHub-specific features, refer to the GitHub documentation at https://docs.github.com and the GitHub CLI documentation at https://cli.github.com.

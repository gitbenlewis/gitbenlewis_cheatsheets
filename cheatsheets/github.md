# GitHub and Git Cheatsheet

## Repository Setup

```bash
# clone a GitHub repository
git clone https://github.com/USER/REPO.git

# move into the cloned repository
cd REPO

# show the remote repository URLs
git remote -v

# add a GitHub remote named origin
git remote add origin https://github.com/USER/REPO.git

# change the origin remote URL
git remote set-url origin https://github.com/USER/REPO.git
```

## Status and History

```bash
# show changed files and the current branch
git status

# show a compact commit history
git log --oneline --graph --decorate --all

# show changes that are not staged
git diff

# show staged changes
git diff --staged

# show the current branch name
git branch --show-current
```

## Stage, Commit, and Push

```bash
# stage all changed files
git add .

# stage one file
git add path/to/file

# commit staged changes
git commit -m "describe the change"

# push the current branch
git push

# push a new branch and set upstream tracking
git push -u origin branch-name
```

## Pull and Sync

```bash
# pull newest changes for the current branch
git pull

# fetch remote changes without merging
git fetch

# pull using rebase for a linear local history
git pull --rebase

# show local branches and remote tracking info
git branch -vv
```

## Branches

```bash
# list local branches
git branch

# create and switch to a new branch
git switch -c branch-name

# switch to an existing branch
git switch branch-name

# rename the current branch
git branch -m new-branch-name

# delete a local branch
git branch -d branch-name

# delete a remote branch
git push origin --delete branch-name
```

## Merge Basics

```bash
# switch to the branch that should receive changes
git switch main

# merge another branch into the current branch
git merge branch-name

# stop a merge with conflicts before committing
git merge --abort

# continue after fixing conflicts
git add .
git commit
```

## Undo Common Mistakes

```bash
# unstage a file but keep edits
git restore --staged path/to/file

# discard unstaged edits in one file
git restore path/to/file

# amend the most recent commit message
git commit --amend -m "new message"

# create a new commit that reverses an old commit
git revert COMMIT_SHA
```

## GitHub CLI

```bash
# authenticate GitHub CLI
gh auth login

# create a pull request
gh pr create --fill

# list pull requests
gh pr list

# view checks for the current pull request
gh pr checks

# open the current repo in the browser
gh repo view --web
```

# Git Cheat Sheet

## Configuration
`git config --global user.name "[name]"`
`git config --global user.email "[email address]"`

## Creating Repositories
`git init [project name]`
`git clone [url]`

## Basic Commands
`git status`
`git add [file]`
`git add .`
`git commit -m "[commit message]"`
`git log`
`git diff`

## Branching
`git branch`
`git branch [branch name]`
`git switch -c [branch name]`
`git merge [branch name]`
`git branch -d [branch name]`

## Remote Repositories
`git remote add [name] [url]`
`git push [remote name] [branch name]`
`git pull [remote name]`

## Undoing Changes
`git reset [commit]`
`git revert [commit]`
`git stash`
`git stash pop`

# 09: Git Cheat Sheet

This is a quick reference for the most common Git commands.

## Configuration

- `git config --global user.name "[name]"`: Set your name for all repositories.
- `git config --global user.email "[email]"`: Set your email for all repositories.
- `git config --list`: List all Git configurations.

## Getting Started

- `git init`: Initialize a new Git repository in the current directory.
- `git clone [url]`: Clone (download) a repository into a new directory.

## The Day-to-Day Workflow

- `git status`: Check the status of your working directory and staging area.
- `git add [file]`: Add a file to the staging area.
- `git add .`: Add all new and modified files in the current directory to the staging area.
- `git commit -m "[message]"`: Commit your staged changes with a message.
- `git log`: View the commit history.
- `git diff`: Show changes between your working directory and the staging area.
- `git diff --staged`: Show changes between the staging area and the last commit.

## Branching

- `git branch`: List all local branches.
- `git branch [branch-name]`: Create a new branch.
- `git switch [branch-name]`: Switch to a different branch.
- `git switch -c [branch-name]`: Create a new branch and switch to it.
- `git merge [branch-name]`: Merge a branch into your current branch.
- `git branch -d [branch-name]`: Delete a branch (only if merged).
- `git branch -D [branch-name]`: Force delete a branch.

## Remote Repositories

- `git remote -v`: List all remote repositories.
- `git remote add [name] [url]`: Add a new remote repository.
- `git push [remote] [branch]`: Push your commits to a remote repository.
- `git pull [remote] [branch]`: Fetch and merge changes from a remote repository.

## Undoing Changes

- `git reset [file]`: Unstage a file, but keep the changes in the working directory.
- `git reset --hard [commit]`: **DANGEROUS.** Discard all changes and go back to a specific commit.
- `git revert [commit]`: Create a new commit that undoes the changes of a specific commit.
- `git stash`: Temporarily save your uncommitted changes.
- `git stash pop`: Restore your most recently stashed changes.
- `git clean -dfx`: **DANGEROUS.** Delete all untracked files and directories.

## Advanced

- `git rebase [branch-name]`: Re-apply commits from your current branch onto another branch. **Do not use on public/shared branches.**
- `git cherry-pick [commit]`: Apply a specific commit from another branch to your current branch.

## Mini Project

This mini-project will test your understanding of the basic Git workflow.

1.  **Create a Repository on GitHub:**
    - Go to GitHub and create a new public repository named `git-practice-project`.
    - Do **not** initialize it with a README.

2.  **Clone and Configure:**
    - On your local machine, run `git clone [URL_of_your_repo]`. 
    - `cd git-practice-project`

3.  **First Commit (main branch):**
    - Create a file named `index.html`.
    - Add the following content:
      ```html
      <!DOCTYPE html>
      <html>
      <head><title>Git Practice</title></head>
      <body><h1>Welcome to my Git Project!</h1></body>
      </html>
      ```
    - Add and commit this file to the `main` branch.
    - Push the `main` branch to GitHub: `git push origin main`.

4.  **Feature Branch:**
    - Create a new branch called `feat/add-styles`.
    - Create a new file named `style.css`.
    - Add a simple CSS rule:
      ```css
      body { background-color: #f0f0f0; color: #333; }
      ```
    - In `index.html`, link the stylesheet by adding `<link rel="stylesheet" href="style.css">` inside the `<head>` tag.
    - Add and commit your changes on the `feat/add-styles` branch.

5.  **Create a Merge Conflict:**
    - Switch back to the `main` branch: `git switch main`.
    - Edit the `<h1>` in `index.html` to say: `<h1>My Awesome Git Project!</h1>`
    - Add and commit this change to the `main` branch.

6.  **Resolve the Conflict:**
    - Try to merge your feature branch: `git merge feat/add-styles`.
    - You will get a merge conflict in `index.html`.
    - Open `index.html` and resolve the conflict. Keep the heading from `main` and the stylesheet link from the feature branch.
The final `index.html` should look like this:
      ```html
      <!DOCTYPE html>
      <html>
      <head>
          <title>Git Practice</title>
          <link rel="stylesheet" href="style.css">
      </head>
      <body><h1>My Awesome Git Project!</h1></body>
      </html>
      ```
    - After editing the file, `git add index.html` and then `git commit` to finalize the merge.

7.  **Push to GitHub:**
    - Push your merged `main` branch to GitHub.
    - `git push origin main`

**Congratulations!** You have just completed a full, realistic Git workflow, including creating a conflict and resolving it. You can now confidently use Git for your own projects.

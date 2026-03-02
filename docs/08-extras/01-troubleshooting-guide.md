# Troubleshooting Guide

Here are some common Git problems and how to solve them:

*   **"I committed to the wrong branch!"**
    *   Use `git reset HEAD~ --soft` to undo the last commit, then `git stash` to save the changes. Switch to the correct branch and `git stash pop` to apply the changes.

*   **"I made a typo in my last commit message!"**
    *   Use `git commit --amend` to edit the last commit message.

*   **"I accidentally deleted a file!"**
    *   Use `git checkout HEAD <file-path>` to restore the file from the last commit.

*   **"My push was rejected!"**
    *   This usually means there are changes on the remote that you don't have locally. Run `git pull --rebase` to pull the latest changes and re-apply your commits on top.

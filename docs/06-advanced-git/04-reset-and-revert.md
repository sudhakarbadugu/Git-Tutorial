# Reset and Revert

There are several ways to undo changes in Git. Here are some of the most common commands:

### `git reset`

`git reset` is used to unstage files or to reset your branch to a previous commit. There are three main modes:

*   `--soft`: Un-commits changes, but leaves them staged.
*   `--mixed` (default): Un-commits and unstages changes, but leaves them in the working directory.
*   `--hard`: Un-commits, unstages, and deletes the changes. **Use with caution!**

`# Go back to the previous commit, keeping changes in the working directory`
`git reset HEAD~`

`# Go back two commits, deleting all changes`
`git reset --hard HEAD~2`

### `git revert`

`git revert` creates a new commit that undoes the changes from a previous commit. This is a safer way to undo changes on a shared branch because it doesn't change the project history.

`git revert <commit-hash>`

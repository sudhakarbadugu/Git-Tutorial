
# 06: Merge Conflicts and Undoing Changes

Sometimes, things go wrong. You might make a mistake, or Git might not be able to merge branches automatically. This section covers how to handle these situations.

## What is a Merge Conflict?

A merge conflict occurs when Git is unable to automatically resolve differences in code between two commits. This usually happens when the same line of code is changed in two different branches that are being merged.

When a merge conflict occurs, Git will stop the merge process and wait for you to resolve the conflict manually.

## How to Resolve a Merge Conflict

When a merge conflict happens, Git will mark the conflicting area in the file like this:

```
<<<<<<< HEAD
This is the content from the current branch.
=======
This is the content from the branch being merged.
>>>>>>> other-branch-name
```

To resolve the conflict, you need to:

1.  **Open the file** in your code editor.
2.  **Edit the file** to keep the changes you want. You can choose one version or the other, or you can combine them.
3.  **Remove the conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`).
4.  **Add the resolved file** to the staging area (`git add <file-name>`).
5.  **Commit the merge** (`git commit`).

## Undoing Changes

There are several ways to undo changes in Git. Here are some of the most common commands:

### `git reset`

`git reset` is used to unstage files or to reset your branch to a previous commit. There are three main modes:

*   `--soft`: Un-commits changes, but leaves them staged.
*   `--mixed` (default): Un-commits and unstages changes, but leaves them in the working directory.
*   `--hard`: Un-commits, unstages, and deletes the changes. **Use with caution!**

```bash
# Go back to the previous commit, keeping changes in the working directory
git reset HEAD~

# Go back two commits, deleting all changes
git reset --hard HEAD~2
```

### `git revert`

`git revert` creates a new commit that undoes the changes from a previous commit. This is a safer way to undo changes on a shared branch because it doesn't change the project history.

```bash
git revert <commit-hash>
```

### `git stash`

Sometimes you need to switch branches, but you're not ready to commit your current work. `git stash` to the rescue!

`git stash` takes your modified tracked files, stages changes, and saves them on a stack of unfinished changes that you can reapply at any time.

```bash
# Stash your changes
git stash

# Reapply the last stashed changes
git stash pop
```

## Common Mistakes Beginners Make

*   **Resolving conflicts by just deleting the markers:** You need to actually decide which code to keep.
*   **Using `git reset --hard` on a shared branch:** This can cause problems for your collaborators.
*   **Committing merge conflict markers:** Always double-check your files before committing a merge.

## Practice Exercises

1.  Create a new branch and make a change to a file.
2.  Switch back to the `main` branch and make a different change to the same line in the same file.
3.  Try to merge the branch and cause a conflict.
4.  Resolve the conflict.
5.  Use `git reset` to undo a commit.
6.  Use `git revert` to undo a commit.

In the next section, we'll discuss some best practices for using Git.

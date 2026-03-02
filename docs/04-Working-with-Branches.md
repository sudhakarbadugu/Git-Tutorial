
# 04: Working with Branches

Branching is one of the most powerful features of Git. It allows you to diverge from the main line of development and continue to do work without messing with that main line.

## What is a Branch?

A branch is essentially a unique set of code changes with a unique name. Each repository has a default branch, which is usually called `main` or `master`.

When you create a branch, you are creating a new pointer to a commit. It's a very lightweight operation.

Here's a diagram showing a repository with two branches:

```
          (feature-branch)
         /
C1---C2---C3 (main)
```

## Creating a New Branch

To create a new branch, you use the `git branch` command:

```bash
git branch <branch-name>
```

For example, to create a new branch called `new-feature`:

```bash
git branch new-feature
```

This creates the branch but doesn't switch to it.

## Switching Branches

To switch to a different branch, you can use the `git checkout` or `git switch` command.

Using `git switch` (the modern way):

```bash
git switch <branch-name>
```

Using `git checkout`:

```bash
git checkout <branch-name>
```

You can also create a new branch and switch to it in one command:

```bash
git switch -c <branch-name>
# or
git checkout -b <branch-name>
```

## Merging Branches

Once you've finished working on your feature in a separate branch, you'll want to merge it back into the `main` branch.

First, switch to the branch you want to merge into (usually `main`):

```bash
git switch main
```

Then, use the `git merge` command:

```bash
git merge <branch-name>
```

This will create a new "merge commit" in the `main` branch that ties the histories of both branches together.

## Deleting a Branch

After you have merged a branch and no longer need it, you can delete it:

```bash
git branch -d <branch-name>
```

The `-d` flag will only delete the branch if it has been successfully merged. To force deletion, use `-D`.

## Common Mistakes Beginners Make

*   **Forgetting which branch they are on:** Always use `git status` or `git branch` to check your current branch before making changes.
*   **Making new commits on the `main` branch directly:** It's a best practice to do new work on a feature branch.
*   **Force deleting a branch (`-D`) that hasn't been merged:** This can lead to losing work.

## Practice Exercises

1.  From your `my-git-project` repository, create a new branch called `test-branch`.
2.  Switch to the `test-branch`.
3.  Create a new file called `test.txt`.
4.  Add and commit the new file.
5.  Switch back to the `main` branch.
6.  Merge the `test-branch` into `main`.
7.  Delete the `test-branch`.

In the next section, we will learn how to work with remote repositories on platforms like GitHub.

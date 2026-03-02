# What are Branches?

A branch is essentially a unique set of code changes with a unique name. Each repository has a default branch, which is usually called `main` or `master`.

When you create a branch, you are creating a new pointer to a commit. It's a very lightweight operation.

## Creating a New Branch

To create a new branch, you use the `git branch` command:

`git branch <branch-name>`

For example, to create a new branch called `new-feature`:

`git branch new-feature`

This creates the branch but doesn't switch to it.

## Switching Branches

To switch to a different branch, you can use the `git checkout` or `git switch` command.

Using `git switch` (the modern way):

`git switch <branch-name>`

Using `git checkout`:

`git checkout <branch-name>`

You can also create a new branch and switch to it in one command:

`git switch -c <branch-name>`
`# or`
`git checkout -b <branch-name>`

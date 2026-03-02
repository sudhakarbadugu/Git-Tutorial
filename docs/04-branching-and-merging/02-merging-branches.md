# Merging Branches

Once you've finished working on your feature in a separate branch, you'll want to merge it back into the `main` branch.

First, switch to the branch you want to merge into (usually `main`):

`git switch main`

Then, use the `git merge` command:

`git merge <branch-name>`

This will create a new "merge commit" in the `main` branch that ties the histories of both branches together.

## Deleting a Branch

After you have merged a branch and no longer need it, you can delete it:

`git branch -d <branch-name>`

The `-d` flag will only delete the branch if it has been successfully merged. To force deletion, use `-D`.

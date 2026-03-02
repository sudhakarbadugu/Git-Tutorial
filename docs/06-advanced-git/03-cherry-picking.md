# Cherry Picking

`git cherry-pick` is a command that allows you to pick a single commit from one branch and apply it to another.

This can be useful if you accidentally made a commit to the wrong branch, or if you only want to incorporate one specific change from a feature branch.

To use it, you need the hash of the commit you want to pick:

`git cherry-pick <commit-hash>`

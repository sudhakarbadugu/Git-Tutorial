# The Staging Area

The `git status` command is your best friend. It shows the state of the working directory and the staging area.

`git status`

This command will tell you which files are:

*   **Tracked:** Files that Git knows about.
*   **Untracked:** Files that are in your working directory but not yet part of your Git repository.
*   **Modified:** Tracked files that have been changed.
*   **Staged:** Modified files that you have marked to go into your next commit.

## Tracking New Files

To start tracking a new file, you use the `git add` command. This command adds the file to the staging area.

To add a specific file:

`git add <filename>`

To add all new and modified files in the current directory:

`git add .`

# Merge Conflicts

A merge conflict occurs when Git is unable to automatically resolve differences in code between two commits. This usually happens when the same line of code is changed in two different branches that are being merged.

When a merge conflict occurs, Git will stop the merge process and wait for you to resolve the conflict manually.

## How to Resolve a Merge Conflict

When a merge conflict happens, Git will mark the conflicting area in the file like this:

`<<<<<<< HEAD`
`This is the content from the current branch.`
`=======`
`This is the content from the branch being merged.`
`>>>>>>> other-branch-name`

To resolve the conflict, you need to:

1.  **Open the file** in your code editor.
2.  **Edit the file** to keep the changes you want. You can choose one version or the other, or you can combine them.
3.  **Remove the conflict markers** (`<<<<<<<`, `=======`, `>>>>>>>`).
4.  **Add the resolved file** to the staging area (`git add <file-name>`).
5.  **Commit the merge** (`git commit`).

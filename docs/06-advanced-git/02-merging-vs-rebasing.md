# Merging vs. Rebasing

Both `git merge` and `git rebase` are used to integrate changes from one branch into another. However, they do it in different ways.

| Feature              | `git merge`                                       | `git rebase`                                                 |
| -------------------- | ------------------------------------------------- | ------------------------------------------------------------ |
| **History**          | Preserves the original history of the branches.   | Rewrites the commit history to create a linear history.      |
| **Merge Commits**    | Creates a new "merge commit".                     | Does not create a merge commit.                              |
| **Collaboration**    | Good for shared branches where history is important. | Can be dangerous on shared branches if not used carefully.     |
| **Readability**      | Can lead to a complex, branching history.         | Results in a clean, easy-to-read, linear history.          |
| **Use Case**         | Merging a feature branch into `main`.             | Updating a feature branch with the latest changes from `main`. |

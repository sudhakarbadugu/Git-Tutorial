# Keeping a Clean History

A clean, linear commit history is easy to read and understand. Here are some tips for keeping your history clean:

*   **Make small, atomic commits:** Each commit should focus on a single, logical change.
*   **Use a consistent commit message format:** This makes the history easier to scan.
*   **Use interactive rebase to clean up your local commits before pushing:** You can squash small commits together, reword commit messages, and reorder commits to create a more logical sequence.
*   **Use `git pull --rebase` instead of `git pull`:** This will re-apply your local commits on top of the latest changes from the remote, avoiding unnecessary merge commits.

**Example of a messy history:**

`*   Merge branch 'main' of ...`
`*   fix typo`
`*   wip`
`*   add feature`
`*   oops`

**Example of a clean history:**

`*   feat(auth): Add password reset functionality`
`*   docs(readme): Update installation instructions`
`*   fix(api): Correctly handle null values in response`

# 07: Git Best Practices

Following best practices will help you and your team work more effectively with Git.

## Commit Often, Perfect Later

- **Make small, atomic commits:** Each commit should represent a single logical change. This makes it easier to understand the history and to revert changes if something goes wrong.
- **Don't wait to have a perfect feature to commit:** Commit your work at the end of each day, or even more frequently. You can always clean up your commits later using interactive rebase.

## Write Good Commit Messages

A good commit message has two parts: a short subject line and a longer body.

- **Subject Line (max 50 chars):**
  - Capitalize the subject line.
  - Do not end the subject line with a period.
  - Use the imperative mood (e.g., "Add feature" not "Added feature").
- **Body (optional):**
  - Explain the *what* and *why* of the change, not the *how*. The code itself shows the *how*.
  - Wrap the body at 72 characters.
  - Use bullet points if necessary.

**Good Example:**

```
feat: Add user authentication endpoint

- Implement JWT-based authentication for the /api/login route.
- The endpoint validates user credentials and returns a signed token.
- This addresses the need for securing API access as per Story-123.
```

**Bad Example:**

```
updated stuff
```

## Use Branches Effectively

- **`main` is sacred:** The `main` (or `master`) branch should always be stable and deployable. Never push directly to `main`.
- **Use feature branches:** Create a new branch for every new feature, bug fix, or experiment.
  - Name your branches descriptively (e.g., `feat/user-login`, `fix/navbar-bug`).
- **Keep branches short-lived:** Merge your feature branches back into `main` as soon as they are complete and tested. Long-running branches are more likely to have merge conflicts.

## The "Golden Rule of Rebase"

- **`git rebase` is for cleaning up your *local*, *private* history.**
- **Never rebase a branch that has been pushed to a remote and is being used by others.** Rebasing rewrites history, which will cause major problems for anyone who has based their work on the original history. Use `git merge` for shared branches.

## Use a `.gitignore` file

- Every Git repository should have a `.gitignore` file.
- This file tells Git which files and directories to ignore and not track.
- Common things to ignore include:
  - Log files
  - Build artifacts (`/dist`, `/build`)
  - Node modules (`/node_modules`)
  - Environment variables (`.env`)
  - OS-specific files (`.DS_Store`, `Thumbs.db`)

You can find pre-made `.gitignore` templates for your specific programming language or framework at [gitignore.io](https://www.toptal.com/developers/gitignore).

## Practice Exercises

1.  Look at the commit history of a public project on GitHub. Find examples of good and bad commit messages.
2.  Create a `.gitignore` file in your `my-git-project` and add entries to ignore `.log` files and a directory called `dist/`.
3.  Create a new file `app.log`. Run `git status`. Does Git see the file? Why or why not?
4.  Explain in your own words: why should you not rebase a public branch?

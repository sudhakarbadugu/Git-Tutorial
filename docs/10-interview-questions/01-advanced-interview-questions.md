# Advanced & Real-World Interview Questions

1.  **You've just run `git push --force` on the `main` branch to fix a mistake, but your teammates had already pulled the old history. What is the exact sequence of commands you and your team need to run to recover without losing anyone's work?**

    **Answer:** First, communicate immediately. Tell everyone to stop pulling and pushing to `main`.
    
    For any teammate who has **not** started new work:
    ```bash
    git fetch origin
    git reset --hard origin/main
    ```

    For any teammate who **has** local commits based on the old history:
    ```bash
    git fetch origin
    # Re-applies their local commits on top of the new, force-pushed main
    git rebase origin/main
    ```

2.  **A junior developer on your team accidentally committed an API key to a public repository and pushed it. Walk me through the steps you would take to completely remove the key from the repository's history.**

    **Answer:**
    1.  **Invalidate the Key:** Immediately revoke the API key with the service provider. This is the most critical step.
    2.  **Clean the History:** Use a tool like `git filter-repo` (preferred) or BFG Repo-Cleaner. The old `git filter-branch` is much slower and more complex.
        ```bash
        # Example using git-filter-repo
        git filter-repo --invert-paths --path path/to/file/with/key.txt
        ```
    3.  **Force Push:** Push the cleaned history to the remote repository.
        ```bash
        git push origin --force --all
        ```
    4.  **Communicate:** Inform the team they will need to re-clone the repository or rebase their existing branches on the newly cleaned history.
    5.  **Prevent Future Issues:** Implement a secret scanning tool or a pre-commit hook to prevent this from happening again.

3.  **Describe a situation where you would choose `git rebase` over `git merge` for integrating a feature branch into `main`, and what are the potential risks associated with that choice in a team environment?**

    **Answer:**
    *   **When to Choose `rebase`:** Use `rebase` on your local feature branch just before merging it into `main`. This creates a clean, linear history on the `main` branch, making it much easier to read, understand, and bisect. The command sequence would be `git fetch origin main` followed by `git rebase origin/main` on your feature branch.
    *   **Potential Risks:** The primary risk is **never rebase a shared, public branch** (like `main` or `develop`). Rebasing rewrites commit history (changing commit SHAs). If other developers have based their work on the original branch, it will cause duplicate commits and significant confusion for the team. Only rebase local branches that you haven't shared yet.

4.  **Your CI build is failing on a pull request due to a merge conflict with the `main` branch that GitHub can't resolve automatically. How do you fix this locally, and what commands would you use to update the PR branch?**

    **Answer:**
    1.  **Check out the PR branch:** `git checkout your-feature-branch`
    2.  **Pull the latest `main` branch to create the conflict locally:** `git pull origin main`
    3.  **Resolve the conflict:** Open the conflicted file(s), remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`), and edit the code to the correct state.
    4.  **Stage the resolved files:** `git add .`
    5.  **Commit the merge:** `git commit -m "Resolved merge conflict with main"`
    6.  **Push the changes to update the PR:** `git push origin your-feature-branch`

5.  **You need to revert a specific commit from three weeks ago that is now buried under 50 other commits on the `main` branch. How would you do this safely without rewriting the public history?**

    **Answer:** Use `git revert <commit-hash>`. This command creates a *new* commit that undoes the changes from the specified commit. It is safe for public history because it doesn't delete or alter existing commits; it simply adds a new one on top, preserving the project's history.

6.  **Explain how you would use `git bisect` to track down a bug that was introduced sometime in the last 200 commits.**

    **Answer:** `git bisect` uses a binary search to find the exact commit that introduced a bug.
    1.  **Start the session:** `git bisect start`
    2.  **Identify a known "bad" commit** (usually `HEAD`): `git bisect bad HEAD`
    3.  **Identify the last known "good" commit:** `git bisect good <commit-hash-from-before-the-bug>`
    4.  **Test and Repeat:** Git will check out a commit in the middle of the range. You test the code. If the bug is present, run `git bisect bad`. If not, run `git bisect good`. Git continues this process until it pinpoints the exact commit.
    5.  **End the session:** `git bisect reset`

7.  **You're about to open a pull request, but you notice your feature branch has 15 small, messy commits. How do you clean up your branch history to present a single, coherent commit for review?**

    **Answer:** Use **interactive rebase**.
    1.  Start the rebase: `git rebase -i HEAD~15`
    2.  An editor will open. Leave `pick` for the first commit, and change the rest from `pick` to `s` (for `squash`) or `f` (for `fixup`) to combine them into the previous one.
    3.  Save and close. A new editor window will open, allowing you to write a single, clean commit message for the combined commit.

8.  **We are migrating from a monolithic repository to multiple microservices. How would you use Git to split a subdirectory of the monorepo into a new, separate repository while preserving its entire commit history?**

    **Answer:** The modern and best tool for this is `git filter-repo`.
    1.  Make a fresh clone of the monorepo.
    2.  Run `git filter-repo` to isolate the subdirectory's history. This command makes the subdirectory the new root of the project.
        ```bash
        git filter-repo --path path/to/your/subdirectory/
        ```
    3.  Add a new remote URL for the new microservice repository: `git remote add new-origin <new-repo-url>`
    4.  Push the filtered history to the new repository: `git push -u new-origin main`

9.  **A pull request has been approved, but the project requires all commits on the `main` branch to be GPG signed. How do you configure Git to sign your commits, and how would you fix unsigned commits in your PR?**

    **Answer:**
    *   **Configuration:**
        ```bash
        # Tell git your GPG key ID
        git config --global user.signingkey YOUR_KEY_ID
        # Tell git to sign all commits automatically
        git config --global commit.gpgsign true
        ```
    *   **Fixing Unsigned Commits:** Use interactive rebase to edit each commit.
        1.  `git rebase -i HEAD~N` (where N is the number of commits in your PR).
        2.  Mark each commit with `e` (`edit`).
        3.  For each commit, amend it with a signature: `git commit --amend --no-edit -S`.
        4.  Continue the rebase: `git rebase --continue`.
        5.  Finally, force-push the updated branch: `git push --force-with-lease`

# Feature Branch Workflow

The Feature Branch Workflow is a popular and effective way to manage changes in a collaborative project. Here's a step-by-step guide:

1.  **Start from a Clean Slate:** Before starting any new work, make sure your local `main` branch is up-to-date with the remote repository.
    `git switch main`
    `git pull origin main`

2.  **Create a Feature Branch:** Create a new branch specifically for your task. This keeps your work isolated.
    `git switch -c feat/about-us-page`

3.  **Do the Work (Code and Commit):** Make your changes and create small, logical commits.
    `git add .`
    `git commit -m "feat: Add initial structure for About Us page"`

4.  **Push Your Feature Branch:** Push your branch to the remote repository.
    `git push -u origin feat/about-us-page`

5.  **Open a Pull Request (PR):** Go to GitHub and open a Pull Request to merge your feature branch into the `main` branch.

6.  **Review and Discussion:** Your teammates will review your code and may request changes.

7.  **Merge the Pull Request:** Once your PR is approved, it can be merged into the `main` branch.

8.  **Clean Up:** After your branch is merged, delete it.
    `git switch main`
    `git pull origin main`
    `git branch -d feat/about-us-page`

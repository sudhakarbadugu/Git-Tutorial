# 08: Real-World Workflow Example

Let's put everything together and walk through a common, practical workflow that you might use on a real project.

This workflow is often called **Feature Branch Workflow**.

## The Scenario

Imagine you are working on a team building a new website. The project is hosted on GitHub. You've been assigned a task to create a new "About Us" page.

## Step-by-Step Workflow

### 1. Start from a Clean Slate

Before starting any new work, make sure your local `main` branch is up-to-date with the remote repository.

```bash
# Switch to the main branch
git switch main

# Pull the latest changes from the remote 'origin'
git pull origin main
```

### 2. Create a Feature Branch

Create a new branch specifically for your task. This keeps your work isolated.

```bash
# Create a new branch for the 'About Us' page and switch to it
git switch -c feat/about-us-page
```

### 3. Do the Work (Code and Commit)

Now, you can start coding! Create the HTML and CSS files for the new page.

As you make progress, create small, logical commits.

```bash
# Create the about.html file
# ... write some HTML ...

# Stage and commit the new file
git add about.html
git commit -m "feat: Add initial structure for About Us page"

# Add some styling to style.css for the new page
# ... write some CSS ...

# Stage and commit the styling changes
git add style.css
git commit -m "feat: Add styling for About Us page"
```

### 4. Push Your Feature Branch

Once you are happy with your work (or you want to get feedback), push your branch to the remote repository (`origin`).

The `-u` flag sets up a tracking relationship between your local branch and the remote branch. This means next time you can just run `git push`.

```bash
git push -u origin feat/about-us-page
```

### 5. Open a Pull Request (PR)

Now, go to the project's repository on GitHub.

- You will see a notification prompting you to create a Pull Request for the branch you just pushed.
- Click on it, and fill out the PR template.
- **Title:** A clear, concise summary of the change (e.g., "Feat: Create About Us page").
- **Description:** Explain what you did and why. If it fixes an issue, reference it (e.g., "Closes #42").
- **Assign reviewers:** Request a review from your teammates.

### 6. Review and Discussion

Your teammates will now review your code. They might leave comments or request changes.

- If they request changes, go back to your code editor, make the changes on your feature branch, and commit and push them again.
- The Pull Request will update automatically with your new commits.

```bash
# ... make changes based on feedback ...
git add .
git commit -m "fix: Update font size on About Us page per review"
git push
```

### 7. Merge the Pull Request

Once your PR is approved, it can be merged into the `main` branch.

- Usually, a project lead or the person who approved the PR will perform the merge using the GitHub interface.
- GitHub provides a few merge options:
  - **Create a merge commit:** This is the default. It keeps all of the feature branch's commits and adds a new merge commit.
  - **Squash and merge:** This combines all of your feature branch commits into a single commit on the `main` branch. This keeps the `main` branch history clean and tidy.
  - **Rebase and merge:** This re-applies your feature branch commits on top of the `main` branch. This creates the cleanest, linear history.

### 8. Clean Up

After your branch is merged, it's good practice to delete it.

- You can delete the remote branch using the button in the GitHub PR.
- You should also delete your local copy of the branch.

```bash
# First, update your local main branch again
git switch main
git pull origin main

# Now, delete the local feature branch
git branch -d feat/about-us-page
```

And that's it! You are now ready to start the process all over again for your next task.

## Practice Exercises

1.  Take your `my-git-project` and push it to a new GitHub repository.
2.  Create a new branch called `docs/add-license`.
3.  On that branch, add a `LICENSE` file (you can just use a standard MIT License template).
4.  Push the branch to GitHub.
5.  Open a Pull Request to merge `docs/add-license` into `main`.
6.  Merge the PR on GitHub using the "Squash and merge" option.
7.  Pull the changes locally and delete the local `docs/add-license` branch.

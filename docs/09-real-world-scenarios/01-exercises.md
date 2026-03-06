# Real-World Scenarios

Now that you've learned the theory and commands, it's time to put your skills to the test with some real-world scenarios. These exercises are designed to simulate common situations you'll encounter in a professional development environment.

## Scenario 1: The Emergency Hotfix 🔥

**Situation:** You are working on a new feature in your `feature-login` branch. Suddenly, a critical bug is reported in production (the `main` branch). You need to pause your current work, fix the bug, and deploy it immediately.

**Goal:** Create a hotfix branch from `main`, apply the fix, merge it back into `main`, and then return to your feature work.

**Steps:**

1.  **Stash your changes:** You have uncommitted changes in `feature-login`. Use `git stash` to save them for later.
2.  **Switch to main:** `git checkout main` (or `git switch main`).
3.  **Create a hotfix branch:** `git checkout -b hotfix-critical-bug`.
4.  **Simulate the fix:** Create a file named `bugfix.txt` with the content "Critical bug fixed!".
5.  **Commit the fix:** Stage and commit the file.
6.  **Merge into main:** Switch back to `main` and merge the hotfix branch.
7.  **Tag the release:** Tag this commit as `v1.0.1`.
8.  **Return to work:** Switch back to `feature-login` and use `git stash pop` to retrieve your work.

**Challenge:** Can you also merge this hotfix into a `develop` branch to ensure the fix is included in future releases?

## Scenario 2: Converting to GitFlow twisted_rightwards_arrows

**Situation:** You've been working on a project with a simple "commit to main" workflow. As the team grows, you decide to adopt the **GitFlow** workflow to manage releases better.

**Goal:** Set up the `develop` branch and simulate a full feature lifecycle.

**Steps:**

1.  **Initialize the repo:** Create a new directory and run `git init`.
2.  **Create main history:** Create a `README.md` and make a commit on `main`.
3.  **Create develop:** Create a branch named `develop` from `main`. This will be your main integration branch.
4.  **Start a feature:** Create a branch `feature-profile` from `develop`.
5.  **Work on feature:** Add a file `profile.html` and commit it.
6.  **Finish feature:** Merge `feature-profile` into `develop` (not `main`!). Delete the feature branch.
7.  **Prepare a release:** Create a branch `release-1.0` from `develop`.
8.  **Finalize release:** Merge `release-1.0` into **both** `main` and `develop`. Tag `main` with `v1.0`.

## Scenario 3: The "Oops" Moment 🙈

**Situation:** You committed a file `secret-keys.txt` that contains sensitive API keys. You need to remove it from the history completely, not just delete it in a new commit.

**Goal:** Use interactive rebase to remove the bad commit.

**Steps:**

1.  **Setup:** Create a new repo. Commit `file1.txt`. Then commit `secret-keys.txt`. Then commit `file2.txt`.
2.  **Identify the bad commit:** Use `git log` to find the commit hash of the "Add secret keys" commit.
3.  **Start rebase:** Run `git rebase -i HEAD~3` (or far enough back to include the bad commit).
4.  **Drop the commit:** In the editor, change the word `pick` to `drop` next to the bad commit.
5.  **Finish rebase:** Save and close the editor.
6.  **Verify:** Run `git log` to confirm the commit is gone.

**Warning:** Never do this on a public branch (like `main`) that others have pulled from!

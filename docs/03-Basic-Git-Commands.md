
# 03: Basic Git Commands

This section covers the basic Git commands you'll use in your daily workflow.

## Initializing a Repository

To start tracking a project with Git, you need to create a new Git repository. You can do this in two ways:

1.  **Initializing a repository in an existing project:**

    If you have an existing project that you want to start tracking with Git, you can navigate to the project's root directory and run:

    ```bash
    git init
    ```

    This command creates a new subdirectory named `.git` that contains all of your necessary repository files – a Git repository skeleton.

2.  **Cloning an existing repository:**

    If you want to get a copy of an existing Git repository — for example, a project you want to contribute to — the command you need is `git clone`.

    ```bash
    git clone <repository-url>
    ```

    For example, to clone the Git-Tutorial repository from GitHub:

    ```bash
    git clone https://github.com/your-username/Git-Tutorial.git
    ```

    This creates a directory named `Git-Tutorial`, initializes a `.git` directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version.

## Checking the Status of Your Files

The `git status` command is your best friend. It shows the state of the working directory and the staging area.

```bash
git status
```

This command will tell you which files are:

*   **Tracked:** Files that Git knows about.
*   **Untracked:** Files that are in your working directory but not yet part of your Git repository.
*   **Modified:** Tracked files that have been changed.
*   **Staged:** Modified files that you have marked to go into your next commit.

## Tracking New Files

To start tracking a new file, you use the `git add` command. This command adds the file to the staging area.

To add a specific file:

```bash
git add <filename>
```

To add all new and modified files in the current directory:

```bash
git add .
```

## Committing Your Changes

Once you have staged the files you want to save, you can commit them. A commit is like a snapshot of your project at a specific point in time.

```bash
git commit -m "Your commit message"
```

The `-m` flag allows you to provide a commit message directly in the command line. A good commit message is short, descriptive, and explains what changes you made and why.

## Viewing the Commit History

To see the history of commits for a repository, you can use the `git log` command.

```bash
git log
```

This will show you a list of all the commits in reverse chronological order.

## Viewing the Differences

The `git diff` command is used to see the changes you've made to your files.

*   `git diff`: Shows the changes between your working directory and the staging area.
*   `git diff --staged`: Shows the changes between the staging area and the last commit.
*   `git diff HEAD`: Shows all the changes in your working directory since the last commit.

## Common Mistakes Beginners Make

*   **Forgetting to `git add` before `git commit`:** This will result in an empty commit.
*   **Writing unhelpful commit messages:** Messages like "updated files" are not very useful. Be descriptive!
*   **Committing large, unrelated changes in a single commit:** Try to make small, atomic commits that focus on a single feature or bug fix.

## Practice Exercises

1.  Create a new directory called `my-git-project`.
2.  Initialize a new Git repository inside this directory.
3.  Create a file named `hello.txt` with some content.
4.  Check the status of the repository. Is the new file tracked?
5.  Add the `hello.txt` file to the staging area.
6.  Check the status again. What has changed?
7.  Commit the file with a descriptive message.
8.  Check the commit history.
9.  Modify the `hello.txt` file.
10. View the differences between your working directory and the last commit.

In the next section, we will learn about one of Git's most powerful features: branching.

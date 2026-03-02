
# 05: Remote Repositories and GitHub

So far, we've been working with a local Git repository. Now it's time to learn how to connect your local repository to a remote repository, like one hosted on GitHub.

## What is a Remote Repository?

A remote repository is a version of your project that is hosted on the internet or a network somewhere. You can have several of them, each of which generally is either read-only or read/write for you.

Collaborating with others involves managing these remote repositories and pushing and pulling data to and from them when you need to share work.

## Adding a Remote Repository

To add a new remote repository, you use the `git remote add` command.

```bash
git remote add <shortname> <url>
```

By convention, the default remote repository is usually named `origin`.

For example, if you've created a new repository on GitHub, you'll be given a URL. You can add it to your local repository like this:

```bash
git remote add origin https://github.com/your-username/your-repository.git
```

## Pushing to a Remote Repository

When you want to share your commits with others, you need to "push" them to the remote repository. The `git push` command is used for this.

```bash
git push <remote-name> <branch-name>
```

To push your local `main` branch to the `origin` remote:

```bash
git push origin main
```

If you have set up a tracking relationship between your local and remote branches, you can simply run `git push`.

## Pulling from a Remote Repository

If other people have made changes to the remote repository, you can get those changes into your local repository by "pulling" them. The `git pull` command does this.

```bash
git pull <remote-name> <branch-name>
```

This command fetches the changes from the remote and merges them into your current branch.

## Pull Requests (PRs)

A Pull Request is a way to contribute to a project on a platform like GitHub. It's not a Git command, but a feature of the hosting platform.

Here's the basic workflow:

1.  **Fork the repository:** Create your own copy of the repository on GitHub.
2.  **Clone your fork:** Clone your forked repository to your local machine.
3.  **Create a branch:** Create a new branch for your changes.
4.  **Make your changes and commit them.**
5.  **Push your branch to your fork.**
6.  **Open a Pull Request:** From your fork on GitHub, you can open a Pull Request to the original repository. This is a request for the project maintainers to "pull" your changes into their repository.

## Common Mistakes Beginners Make

*   **Forgetting to add a remote:** You need to tell Git where your remote repository is.
*   **Pushing to the wrong branch:** Always check which branch you are on before pushing.
*   **Working directly on the `main` branch of a collaborative project:** It's better to work on a feature branch and open a pull request.

## Practice Exercises

1.  Go to GitHub and create a new repository called `hello-world`.
2.  In your `my-git-project` from the previous exercises, add this new GitHub repository as a remote named `origin`.
3.  Push your `main` branch to the `origin` remote.
4.  Verify that your files are now on GitHub.

Next, we'll learn how to deal with the inevitable merge conflicts and how to undo changes in Git.

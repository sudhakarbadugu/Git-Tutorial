# Your First Repository

To start tracking a project with Git, you need to create a new Git repository. You can do this in two ways:

1.  **Initializing a repository in an existing project:**

    If you have an existing project that you want to start tracking with Git, you can navigate to the project's root directory and run:

    `git init`

    This command creates a new subdirectory named `.git` that contains all of your necessary repository files – a Git repository skeleton.

2.  **Cloning an existing repository:**

    If you want to get a copy of an existing Git repository — for example, a project you want to contribute to — the command you need is `git clone`.

    `git clone <repository-url>`

    For example, to clone the Git-Tutorial repository from GitHub:

    `git clone https://github.com/your-username/Git-Tutorial.git`

    This creates a directory named `Git-Tutorial`, initializes a `.git` directory inside it, pulls down all the data for that repository, and checks out a working copy of the latest version.

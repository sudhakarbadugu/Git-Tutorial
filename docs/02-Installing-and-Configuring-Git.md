
# 02: Installing and Configuring Git

Now that you understand what Git is, it's time to install it and set it up on your computer.

## Installing Git

Git is available for all major operating systems: macOS, Windows, and Linux.

### macOS

The easiest way to install Git on a Mac is to install the Xcode Command Line Tools. You can do this by running the following command in your terminal:

```bash
xcode-select --install
```

Alternatively, you can download the latest version of Git from the [official Git website](https://git-scm.com/download/mac).

### Windows

On Windows, you can download the official Git for Windows installer from the [Git website](https://git-scm.com/download/win). This will install both the Git command-line tool and the Git GUI, a graphical user interface for Git.

### Linux

For Linux, you can usually install Git through your distribution's package manager. For example, on Debian/Ubuntu:

```bash
sudo apt-get update
sudo apt-get install git
```

On Fedora:

```bash
sudo dnf install git
```

## Verifying the Installation

Once the installation is complete, you can verify it by opening your terminal and running:

```bash
git --version
```

This should display the installed Git version:

```
git version 2.37.1
```

## Configuring Git

The first thing you should do after installing Git is to set your username and email address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@example.com"
```

Replace `"Your Name"` and `"youremail@example.com"` with your own name and email.

The `--global` flag tells Git to use this configuration for all of your projects. If you want to use a different name or email for a specific project, you can run the same command without the `--global` flag inside that project's directory.

### Checking Your Configuration

You can check your configuration settings with this command:

```bash
git config --list
```

This will show you all your Git configuration settings.

## Common Mistakes Beginners Make

*   **Forgetting to configure Git:** This can lead to commits with incorrect author information.
*   **Using a fake email:** It's best to use your real email address, especially if you plan to contribute to projects on GitHub.
*   **Installing an outdated version:** Make sure you have a recent version of Git to have access to the latest features and bug fixes.

## Practice Exercises

1.  Install Git on your operating system.
2.  Verify the installation and check the Git version.
3.  Configure your username and email address.
4.  Check your Git configuration to make sure your name and email are set up correctly.

Great! You're now ready to start using Git. In the next section, we'll learn some of the most basic and essential Git commands.

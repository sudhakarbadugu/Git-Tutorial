# Installing Git

Git is available for all major operating systems: macOS, Windows, and Linux.

### macOS

The easiest way to install Git on a Mac is to install the Xcode Command Line Tools. You can do this by running the following command in your terminal:

`xcode-select --install`

Alternatively, you can download the latest version of Git from the [official Git website](https://git-scm.com/download/mac).

### Windows

On Windows, you can download the official Git for Windows installer from the [Git website](https://git-scm.com/download/win). This will install both the Git command-line tool and the Git GUI, a graphical user interface for Git.

### Linux

For Linux, you can usually install Git through your distribution's package manager. For example, on Debian/Ubuntu:

`sudo apt-get update`
`sudo apt-get install git`

On Fedora:

`sudo dnf install git`

## Verifying the Installation

Once the installation is complete, you can verify it by opening your terminal and running:

`git --version`

This should display the installed Git version:

`git version 2.37.1`

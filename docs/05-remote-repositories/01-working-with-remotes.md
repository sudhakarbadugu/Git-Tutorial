# Working with Remotes

A remote repository is a version of your project that is hosted on the internet or a network somewhere. You can have several of them, each of which generally is either read-only or read/write for you.

Collaborating with others involves managing these remote repositories and pushing and pulling data to and from them when you need to share work.

## Adding a Remote Repository

To add a new remote repository, you use the `git remote add` command.

`git remote add <shortname> <url>`

By convention, the default remote repository is usually named `origin`.

For example, if you've created a new repository on GitHub, you'll be given a URL. You can add it to your local repository like this:

`git remote add origin https://github.com/your-username/your-repository.git`

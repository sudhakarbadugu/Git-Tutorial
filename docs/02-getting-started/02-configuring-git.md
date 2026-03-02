# Configuring Git

The first thing you should do after installing Git is to set your username and email address. This is important because every Git commit uses this information, and it’s immutably baked into the commits you start creating:

`git config --global user.name "Your Name"`
`git config --global user.email "youremail@example.com"`

Replace `"Your Name"` and `"youremail@example.com"` with your own name and email.

The `--global` flag tells Git to use this configuration for all of your projects. If you want to use a different name or email for a specific project, you can run the same command without the `--global` flag inside that project's directory.

### Checking Your Configuration

You can check your configuration settings with this command:

`git config --list`

This will show you all your Git configuration settings.

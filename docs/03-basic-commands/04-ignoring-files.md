# Ignoring Files

Sometimes, you'll have files in your project that you don't want to track with Git. These could be:

*   Log files
*   Build artifacts
*   Files with sensitive information (like API keys)
*   Operating system junk files (like `.DS_Store` on macOS)

You can tell Git to ignore these files by creating a file named `.gitignore` in your project's root directory.

Each line in the `.gitignore` file specifies a pattern. For example:

```
# Ignore log files
*.log

# Ignore build output
/build

# Ignore a specific file
credentials.json
```

It's a good practice to set up your `.gitignore` file at the beginning of a project.

# ⚡ 10-Minute Quick Start: Your First Git Repository

Want to start using Git *right now*? This guide will get you up and running with your first repository in under 10 minutes. No fluff, just action.

## 🏁 Goal
By the end of this guide, you will have:
1. Created a project.
2. Turned it into a Git repository.
3. Saved your first version of a file.

## 📋 Prerequisites
- **Git installed:** Type `git --version` in your terminal. If you get an error, [install Git here](../02-getting-started/01-installing-git.md).

---

## 🚀 Let's Go!

### 1. Create a Project Folder 📁
Open your terminal (Command Prompt, PowerShell, or Terminal) and type:

```bash
mkdir my-first-repo
cd my-first-repo
```

### 2. Initialize Git 🎬
Tell Git to start watching this folder.

```bash
git init
```
*Output:* `Initialized empty Git repository in ...`

### 3. Create a File 📄
Make a simple file to track.

```bash
echo "# My Project" > README.md
```

### 4. Stage the File 📦
Tell Git: "I want to save this file in the next snapshot."

```bash
git add README.md
```
*(No output is good news!)*

### 5. Commit the Changes 💾
Save the snapshot with a message describing what you did.

```bash
git commit -m "Initial commit"
```
*Output:* `[master (root-commit) ...] Initial commit`

### 6. Verify 🔍
Check your project history to see the save.

```bash
git log
```

---

## 🎉 You Did It!
You just performed the core Git workflow: **Modify** -> **Stage** -> **Commit**.

### ⏩ What's Next?
- **Configure Git:** Set your name and email in [Configuring Git](../02-getting-started/02-configuring-git.md).
- **Learn the Basics:** Deep dive into [Staging](../03-basic-commands/01-the-staging-area.md) and [Commits](../03-basic-commands/02-making-commits.md).

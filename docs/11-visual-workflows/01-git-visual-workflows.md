# Git Visual Workflows

Understanding Git workflows can be challenging with text alone. These diagrams illustrate the most common workflows and concepts to help you visualize how Git operates in a team environment.

---

### 1. General Git Workflow

This diagram shows the fundamental flow of work between a developer's local machine and a central remote repository.

```mermaid
graph LR
    subgraph Developer A
        A[Local Repo]
    end
    
    subgraph Remote Server
        B[Remote Repo]
    end

    subgraph Developer B
        C[Local Repo]
    end

    A -- git push --> B
    B -- git pull --> C
    C -- git push --> B
    B -- git pull --> A

```
**Explanation:** Developers work on their own **Local Repo**. When they are ready to share their changes, they `push` them to the **Remote Repo**. To get the latest changes from others, they `pull` from the **Remote Repo** into their local one.

---

### 2. Git Branch Workflow

This is the most common workflow for developing new features. Work is done on an isolated `feature` branch to keep the `main` branch stable.

```mermaid
gitGraph
   commit id: "Initial Commit"
   branch feat/new-login
   checkout feat/new-login
   commit id: "Add login form"
   commit id: "Add password validation"
   checkout main
   merge feat/new-login
   commit id: "Prepare for release"
```
**Explanation:**
1. The `main` branch contains the stable, production-ready code.
2. A new branch (`feat/new-login`) is created from `main`.
3. All new work and commits are made on the feature branch.
4. Once the feature is complete and tested, it is merged back into `main`.

---

### 3. Fork Workflow

This workflow is common in open-source projects where contributors may not have direct access to the main repository.

```mermaid
graph TD
    subgraph Original Project
        A[Original Repo]
    end
    
    subgraph Contributor
        B[Forked Repo]
        C[Local Clone]
    end

    A -- 1. Fork --> B
    B -- 2. Clone --> C
    C -- 3. git push --> B
    B -- 4. Open Pull Request --> A
```
**Explanation:**
1. A contributor **forks** the original repository, creating a personal copy on their own account.
2. They **clone** their fork to their local machine to work on it.
3. After making changes, they **push** their commits to their forked repository.
4. Finally, they open a **Pull Request** from their fork to the original project, requesting that their changes be merged.

---

### 4. Pull Request Lifecycle

This diagram illustrates the end-to-end process of getting code from a developer's machine into the final product.

```mermaid
sequenceDiagram
    participant Dev
    participant Git Repo
    participant CI/CD System
    participant Reviewer
    participant Production

    Dev->>Git Repo: git push (on feature branch)
    Git Repo->>Dev: Creates Pull Request
    Dev->>Reviewer: Request Code Review
    Reviewer-->>Dev: Provides Feedback/Approval
    Dev->>Git Repo: Merges Pull Request into main
    Git Repo->>CI/CD System: Triggers automated build & test
    CI/CD System-->>Production: Deploys new version
```
**Explanation:** The lifecycle begins when a developer pushes code and opens a Pull Request. After passing a code review and automated checks, the code is merged and automatically deployed.

---

### 5. Merge Conflict Workflow

A merge conflict occurs when Git cannot automatically resolve differences in code between two commits.

```mermaid
gitGraph
   commit id: "Initial Commit"
   branch feat/update-readme
   checkout feat/update-readme
   commit id: "Update title in README"
   checkout main
   commit id: "Change README title"
   checkout feat/update-readme
   merge main
```
**Explanation:** In this diagram, both the `main` and `feat/update-readme` branches modified the same line in the `README` file. When trying to merge `main` into the feature branch, Git detects a **conflict** and pauses the merge, requiring the developer to resolve it manually.

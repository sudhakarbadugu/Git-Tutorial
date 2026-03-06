# GitFlow Overview

GitFlow is a more structured branching model than the Feature Branch Workflow. It's designed for projects with a scheduled release cycle.

## Visualizing GitFlow

Here is a diagram illustrating the GitFlow branching model:

```mermaid
gitGraph
   commit
   branch develop
   checkout develop
   commit
   branch feature-1
   checkout feature-1
   commit
   checkout develop
   merge feature-1
   branch release-1.0
   checkout release-1.0
   commit
   checkout main
   merge release-1.0 tag: "v1.0"
   checkout develop
   merge release-1.0
   branch hotfix-1.0.1
   checkout hotfix-1.0.1
   commit
   checkout main
   merge hotfix-1.0.1 tag: "v1.0.1"
   checkout develop
   merge hotfix-1.0.1
```

It introduces several new types of branches:

*   **`main`:** This branch stores the official release history.
*   **`develop`:** This is the integration branch for new features.
*   **`feature-*`:** These branches are used to develop new features. They branch off of `develop` and are merged back into `develop`.
*   **`release-*`:** These branches are used to prepare for a new production release. They branch off of `develop` and are merged into both `main` and `develop`.
*   **`hotfix-*`:** These branches are used to quickly patch production releases. They branch off of `main` and are merged into both `main` and `develop`.

GitFlow is a powerful workflow, but it can be overly complex for smaller projects.

# What is Version Control?

Imagine you're writing an essay. You write a draft, then make some changes. You might save the new version as `essay_v2.doc`. Then you make more changes and save it as `essay_final.doc`, and then `essay_final_final.doc`. This is a manual form of version control.

Version Control Systems (VCS) are tools that automate this process. They help you track changes to your files over time, allowing you to recall specific versions later.

There are two main types of VCS:

## 1. Centralized Version Control Systems (CVCS)
In a CVCS, a single central server contains all the versions of the files and the entire history of the project. Developers "check out" a working copy from this central server to work on it. (e.g., Subversion, Perforce).

![Centralized Version Control System Diagram](../../assets/images/Centralized%20version%20control%20system%20diagram.png)

*   **How it works:** You connect to a central server to get the latest code and to save your changes.
*   **Pros:** Simple to understand and manage.
*   **Cons:** It has a single point of failure. If the central server goes down, no one can collaborate or save their work. It also requires a constant network connection.

## 2. Distributed Version Control Systems (DVCS)
In a DVCS, every developer has a full, local copy of the entire repository, including its history. (e.g., Git, Mercurial).

![Distributed Version Control System Diagram](../../assets/images/Distributed%20version%20control%20system%20diagram.png)

*   **How it works:** You "clone" an entire repository to your local machine. You can commit changes, create branches, and view history completely offline. To share your changes, you "push" them to a shared remote server.
*   **Pros:** You can work offline, there's no single point of failure (every clone is a full backup), and most operations are much faster because they are done locally.
*   **Cons:** The initial learning curve can be slightly steeper.

## Key Differences at a Glance

| Feature              | Centralized (CVCS)            | Distributed (DVCS)                  |
| -------------------- | ----------------------------- | ----------------------------------- |
| **Core Concept**     | Single central server         | Multiple local copies (clones)      |
| **Offline Capability** | Limited (requires connection) | Full (commit, branch, log offline)  |
| **Performance**      | Slower (network dependent)    | Faster (most operations are local)  |
| **Data Redundancy**  | Low (only on the server)      | High (every clone is a full backup) |
| **Branching/Merging**| Often complex and slow        | Fast, simple, and powerful          |

---

Git is a **Distributed Version Control System**, and its design is the reason it's so fast, flexible, and popular today.

# What is Git?

Git is a free and open-source distributed version control system created by Linus Torvalds in 2005 (the creator of Linux). It's designed to handle everything from small to very large projects with speed and efficiency.

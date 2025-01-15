---
theme:
  override:
    code:
      alignment: left
      background: false
---

# Introduction to Git
_A version control system for tracking changes in computer files._

## Context:
Git is a powerful tool that allows individuals and teams to manage projects by tracking file changes and coordinating work among multiple contributors. It’s used in software development but can also manage files for design, writing, or other collaborative efforts.



<!-- end_slide -->


## What Is Git?
- A **distributed version control system** (DVCS)
- Created by Linus Torvalds in 2005
- Enables collaboration and tracking changes in files over time

## Context:

Distributed means every user has a complete local copy of the entire repository, ensuring faster operations and no single point of failure.
Version Control helps teams avoid overwriting each other’s changes and provides a history of who changed what and when.
Linus Torvalds, the creator of Linux, developed Git to handle large-scale collaboration on the Linux kernel.

<!-- end_slide -->

## Why Use Git?
- **Collaboration**: Multiple contributors can work on the same project.
- **Version History**: Easily review, revert, or compare different versions.
- **Branching & Merging**: Isolate new features and then integrate them seamlessly.
- **Lightweight**: Minimal overhead for creating branches and snapshots.

## Context:

Git makes collaboration smooth by eliminating the need to email files back and forth.
Each commit you make saves a snapshot in time. If you break something, you can revert to a previous state.
Branches allow you to work on new ideas or bug fixes independently. Merging brings your work back into the main project when ready.
Even though Git tracks every version, it stores data very efficiently.

## Context:

Working Directory: This is where you do your actual editing (think “workspace”).
Staging Area: Once you decide which changes should be part of your next “snapshot,” you add them to the staging area.
Local Repo: After you commit your staged changes, Git saves them in your local repository.
Remote Repo: By pushing your local commits to a remote location like GitHub, you enable others to see and collaborate on your changes.

<!-- end_slide -->

## How Git Works
1. **Working Directory**: Your local set of files.
2. **Staging Area** (Index): The list of changes you want to commit.
3. **Local Repository**: Your private database of commits.
4. **Remote Repository**: A shared repository (e.g., on GitHub or GitLab) for collaboration.

<!-- end_slide -->

## Key Git Concepts
- **Commit**: A snapshot of the repository at a specific time.
- **Branch**: A parallel line of development. 
- **Merge**: Combining changes from one branch into another.
- **Pull**: Fetch the latest changes from remote and merge them locally.
- **Push**: Send your local commits to the remote repository.
- **Clone**: Copy an entire remote repository to your local machine.

## Context:

Commit: Think of it like a “save point” in a video game—you can always go back if needed.
Branch: Allows you to work independently so you don’t break the main project.
Merge: Incorporates your branch’s changes into another branch (often the main branch).
Pull: Brings changes from the remote repository to your local environment.
Push: Publishes your local commits so others can access them.
Clone: Useful when you want to get the whole project locally for the first time.

<!-- end_slide -->

## Basic Git Commands
- `git init`: Initialize a new Git repository.
- `git clone <repo_url>`: Clone an existing repository.
- `git status`: Show the state of the working directory and staging area.
- `git add <file>`: Stage file changes for the next commit.
- `git commit -m "Message"`: Commit staged changes with a message.
- `git push`: Upload your local commits to the remote repository.
- `git pull`: Fetch and merge the latest changes from remote.

## Context:

git init: Use in a new project folder to start tracking with Git.
git clone: Grabs an entire repository (and all of its history) onto your machine.
git status: Your go-to command to see which files are modified, staged, or untracked.
git add: Staging changes is a deliberate action; you choose exactly which changes get committed.
git commit: A good commit message explains what you changed and why.
git push: Think of this as “syncing” your local work to the team’s shared space.
git pull: Frequent pulls help keep your local codebase up to date with the team’s changes.

## Context:

Feature Branch Workflow: Encourages organized development, with separate branches for each new feature.
Fork & Pull Request: Great for open-source, where you don’t have write access to the main repo. You “fork” (copy) it, and then request your changes be pulled in.
GitFlow: More complex branching strategy that helps teams with large or long-running projects manage releases and hotfixes.


<!-- end_slide -->

## Common Git Workflows
1. **Feature Branch Workflow**:
   - Create a branch for each feature or bug fix.
   - Merge (or rebase) into main/master when done.
2. **Fork & Pull Request** (used in open-source):
   - Fork a project.
   - Make changes in your fork.
   - Create a pull request to merge into the original repository.
3. **GitFlow**:
   - Structured approach with develop, release, and hotfix branches.
   - Often used for larger projects with formal release cycles.

## Context:

Stashing: You can safely switch branches or pull updates without losing your incomplete edits.
Tagging: Commonly used to label release versions (e.g., v1.0).
Rebase: Can help maintain a tidy commit history, but requires caution to avoid conflicts.
Hooks: Scripts that run automatically—for instance, to enforce coding standards or run tests before committing.
GUI Tools: If command line feels intimidating, use a graphical client or IDE integration for a more visual Git experience.
.gitignore: Prevents accidentally committing large files or sensitive data (like API keys or passwords).


<!-- end_slide -->


## Useful Features & Tips
- **Stashing**: Temporarily save unfinished work (`git stash`).
- **Tagging**: Mark specific commits (e.g., version releases).
- **Rebase**: Rewrite commit history for cleaner, linear history.
- **Hooks**: Automate tasks at certain stages (e.g., pre-commit checks).
- **GUI Tools**: Git clients like GitKraken, Sourcetree, or VS Code built-in Git.
- **Ignore files**: Use `.gitignore` to exclude files from version control.


<!-- end_slide -->

## Resources & Next Steps
- [Official Git Documentation](https://git-scm.com/doc)
- [Pro Git Book (Free)](https://git-scm.com/book)
- [GitHub Guides](https://guides.github.com/)
- **Practice**:
  - Set up a sample project
  - Try making commits, branching, and merging
  - Collaborate with a partner on GitHub or GitLab



<!-- end_slide -->

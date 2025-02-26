# Git Quick Reference

Below is a quick reference of common Git commands to help you manage your repositories.

| **Command**                | **Description**                                                                                      |
|----------------------------|------------------------------------------------------------------------------------------------------|
| `git clone <URL>`         | Clone an existing Git project from the remote repository at `<URL>` into the current directory.      |
| `git status`              | Display the status of files in the working tree (which are staged, unstaged, or untracked).          |
| `git add <file>`          | Stage a new or changed file for the next commit.                                                     |
| `git rm <file>`           | Stage removal of a file for the next commit.                                                          |
| `git reset`               | Unstage files that have been staged for the next commit (or move branch pointer; context needed).     |
| `git commit -m "<message>`| Commit the staged files to the local repository with a descriptive message.                           |
| `git push`                | Push changes in the local repository to the remote repository.                                       |
| `git pull`                | Fetch updates from the remote repository and merge them into the working tree.                       |
| `git revert <commit-hash>`| Create a new commit that undoes the changes in the referenced commit (using its commit hash).         |
| `git init`                | Create a new Git repository in the current directory.                                                 |
| `git log`                 | Display the commit log (history) of messages and hashes.                                              |
| `git show <commit-hash>`  | Shows details for a particular commit, including what changed.                                        |

Use this as a handy cheat-sheet when working with Git. Remember, there are more advanced commands and options, but these are the basics to get you started!


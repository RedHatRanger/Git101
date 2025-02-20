***"An investment in Knowledge pays the best interest" -Ben Franklin***
<br><br>


# What is Git?
![image](https://github.com/user-attachments/assets/7c9e2ab2-33cf-4155-8ecb-1377e791ea54) ![image](https://github.com/user-attachments/assets/f4717836-061d-4094-9ead-a620b2c58b58) ![image](https://github.com/user-attachments/assets/63ca5a7e-825e-402f-a9dc-6cd6fdb8a50e) ![image](https://github.com/user-attachments/assets/588b184e-77e2-4c3a-ae05-6efb8695ae69) ![image](https://github.com/user-attachments/assets/faa90216-e945-4be5-bfbb-1efa19df904b)
 ![image](https://github.com/user-attachments/assets/90336e07-0726-4f0b-8685-4c7e8fabaeef) ![image](https://github.com/user-attachments/assets/e4e80a97-eef4-46a2-95b7-b041944ab292) ![image](https://github.com/user-attachments/assets/6a97cc88-7df1-40cd-9e90-dc494c9340e0)

(photos by: kodekloud.com)

<br><br><br><br>
# Lab 1: Git Setup & Basic Workflows
# The Ultimate Beginner’s Guide to Git: A Kid-Friendly Tutorial

If you’ve ever worked on a group project (like a class poster or a digital slideshow) and wished you could easily undo changes or see who did what, Git is the tool for you! Git is a version control system that helps you track changes to files, collaborate with teammates, and save different versions of your work. By the end of this tutorial, you’ll understand how to get Git set up and use it like a pro — no matter your age.

---

## Table of Contents
1. [What is Git?](#what-is-git)
2. [Installing Git](#installing-git)
3. [Setting Up Your Information](#setting-up-your-information)
4. [Creating or Cloning a Project](#creating-or-cloning-a-project)
5. [Working with Files](#working-with-files)
6. [Saving Your Work (Committing)](#saving-your-work-committing)
7. [Checking What You’ve Done (Log and Status)](#checking-what-youve-done-log-and-status)
8. [Sharing and Getting Updates (Push and Pull)](#sharing-and-getting-updates-push-and-pull)
9. [Fixing Mistakes (Undo and Revert)](#fixing-mistakes-undo-and-revert)
10. [Branches: Working in Parallel](#branches-working-in-parallel)
11. [Extra Tips](#extra-tips)
12. [Practice Lab](#practice-lab)
13. [Further Reading & Next Steps](#further-reading--next-steps)

---

## What is Git?

Imagine you’re writing a story with friends. Each friend wants to add or change parts of the story, sometimes at the same time. Git helps everyone work together on the same set of files without accidentally messing up someone else’s changes. You can always look back at old versions of the story to see what changed or fix mistakes.

Git is often used with an online service (like GitHub, GitLab, or Bitbucket) so everyone’s updates can be shared.

---

## Installing Git

Before you start using Git, you need to install it on your computer.

### Windows
1. Go to [Git for Windows](https://gitforwindows.org/) and download the installer. Follow the steps on screen.
2. Or, open **Command Prompt** or **PowerShell** and run:
   ```powershell
   winget install --id Git.Git -e --source winget
   ```

### macOS
1. Install [Homebrew](https://brew.sh/) if you don’t already have it:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. Use Homebrew to install Git:
   ```bash
   brew install git
   ```

### Linux
- **Debian/Ubuntu**:
  ```bash
  sudo apt update && sudo apt upgrade
  sudo apt install git git-man
  ```
- **Fedora/CentOS**:
  ```bash
  sudo yum install git
  ```
- **Arch Linux**:
  ```bash
  sudo pacman -S git
  ```

#### Check Your Installation
Open your terminal or command prompt and type:
```bash
git --version
```
You should see something like `git version 2.x.x`.

---

## Setting Up Your Information

Git wants to label your work so it knows who changed what.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

This way, every time you save your work, Git can tag it with your name and email.

---

## Creating or Cloning a Project

There are two main ways to start using Git:

1. **Create a fresh project** on your computer.
2. **Copy (clone) a project** from somewhere else (like a remote server).

### 1. Starting from Scratch

In any folder on your computer, run:
```bash
git init
```
This tells Git: “Start watching this folder for changes!” This folder is now a **repository**.

### 2. Cloning an Existing Project

If your team already made a Git repository somewhere else, you can copy (clone) it:
```bash
git clone git@some-server.com:project.git
```
- After cloning, you’ll have a folder on your computer that matches the remote project. Changes you make can eventually be shared (pushed) back to the server.

---

## Working with Files

When you make or change files in your project folder, Git sees that your “working tree” is now **dirty** or has **untracked** files.

### Common Commands:
- **`git status`**: Shows what’s changed, what’s new, and what’s staged (prepared) for saving.
- **`git add <file>`**: Puts your new or changed files into a “staging” area, telling Git you want these to be in your next save (commit).
- **`git rm <file>`**: Removes a file from your folder and stages that removal.
- **`git reset <file>`**: Takes a file out of the staging area, but leaves the file itself alone.

**Example Workflow:**
```bash
# 1. Create a new file:
echo "Hello, world!" > hello.txt

# 2. Check status:
git status

# 3. Stage the new file:
git add hello.txt
```

---

## Saving Your Work (Committing)

Once you’ve added your changed or new files to the staging area, you save them with a **commit**:
```bash
git commit -m "Add hello.txt"
```
- The `-m` flag is a short message describing what you did and **why**.
- You can commit multiple files at once.

**Important:** A commit only includes files that were staged. If you forget to add a file, it won’t be part of the commit.

### Quick Tip: `git commit -a`

You can save a shortcut step with `git commit -a`, which automatically stages **any changed** (but not new) files and commits them. But new files still need `git add` first.

---

## Checking What You’ve Done (Log and Status)

- **`git log`**: Shows a list of all your commits. The newest commit is usually at the top.
- **`git show <commit-hash>`**: Shows the details of a specific commit, including the changes made.

Every commit has a long ID called a **hash** (like `abc1234`). Think of it as a fingerprint for that version of your files.

---

## Sharing and Getting Updates (Push and Pull)

If you’re working with a **remote repository** (a copy of your Git repo stored on a server):

### Pushing Your Changes

- **`git push`**: Sends your latest commits to the remote server so others can see them.
- The first time you push a new branch, you might need to run:
  ```bash
  git push --set-upstream origin <branch-name>
  ```

### Pulling Other People’s Changes

- **`git pull`**: Fetches any new commits from the remote repository and automatically merges them into your files. Think of it like “Get the latest updates from the team.”

---

## Fixing Mistakes (Undo and Revert)

Mistakes happen. Git can help!

- **Discard changes in a file you haven’t committed**:
  ```bash
  git checkout -- <file>
  ```
  This resets the file to how it was at your last commit.

- **Unstage a file** (if you added it by mistake):
  ```bash
  git reset HEAD <file>
  ```

- **Revert a commit** if you want to undo a commit that’s already been saved:
  ```bash
  git revert <commit-hash>
  ```
  This makes a new commit that undoes the changes in that old commit.

---

## Branches: Working in Parallel

A **branch** in Git is like creating a new path in your story, so you can work on a new idea without changing the main plot right away.

### Creating and Switching Branches
```bash
git branch my-new-idea  # Create a new branch

git checkout my-new-idea  # Switch to that branch

# Or do both in one step:
git checkout -b my-new-idea
```

### Merging Branches

Once you like the changes in your branch, you can merge them back into the main branch:
```bash
git checkout main
git merge my-new-idea
```

If the same lines in a file were changed differently in each branch, you’ll get a **merge conflict**. You’ll need to open the files, pick which changes to keep, and then commit.

---

## Extra Tips

- Keep your **commit messages** short but meaningful. The first line should be a quick summary (under 50 characters if possible). Add a blank line, then more details if needed.
- Use **`.gitignore`** to tell Git which files or folders it should skip (like logs or big compiled files you don’t want to track).
- Pull requests (or merge requests) are used on platforms like GitHub or GitLab to discuss and review changes before merging to important branches.

---

## Practice Lab

Below is a short lab to help you practice.

### 1. Objectives
- Install Git.
- Configure your user name and email.
- Initialize a new Git repository or clone an existing one.
- Add and commit files.
- Practice discarding changes.

### 2. Install Git
Follow the instructions in [Installing Git](#installing-git) above.

### 3. Configure Git (Global Settings)
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

### 4. Initialize a New Repository or Clone One
```bash
mkdir my-first-git-project
cd my-first-git-project
git init  # or "git clone <URL>" if you have an existing repo
```

### 5. Create, Stage, and Commit

```bash
echo "This is my first file." > file1.txt
git add file1.txt
git commit -m "Add file1.txt"
```

### 6. View Your Commit Log
```bash
git log --oneline
```

### 7. Discard Changes
- Unstage a file:
  ```bash
  git reset HEAD file1.txt
  ```
- Discard a file’s local changes:
  ```bash
  git checkout -- file1.txt
  ```

---

## Final Thoughts

Congratulations! You’ve just learned the basics of Git. Even if you’re in fifth grade, you can now track changes to your projects, share your work, and roll back to earlier versions when things go wrong. Git might feel like magic at first, but with practice, you’ll see how it helps keep your work organized and safe!

Remember:
1. **Add** files to stage your changes.
2. **Commit** your staged changes with a message.
3. **Push** to share.
4. **Pull** often to stay updated.
5. **Branch** to experiment.

Keep exploring to learn more advanced topics like **merge conflicts**, **pull requests**, and **branch protection**. Have fun and happy coding!

---

## Further Reading & Next Steps

For more advanced topics and hands-on practice, explore the following labs:

- **[Lab 02: Git Branches](02_git_branches.md)** — Learn more about branches, merging, and collaboration with teams.
- **[Lab 03: Git Branch Merging](03_git_branch_merging.md)** — Dive deeper into different ways to merge branches.
- **[Lab 04: Git Remote and Push](04_git_remote_and_git_push.md)** — Set up remote repositories and learn to push your changes.
- **[Lab 05: Git Cloning](05_git_cloning.md)** — Master the process of cloning repositories.
- **[Lab 06: Git Pull Requests](06_git_pull_requests.md)** — Col[Laborate more efficiently on Git hosting platforms.
- **[Lab 07: Git Fetch and Git Pull](07_git_fetch_and_git_pull.md)** — Understand how to bring updates from remote repos.
- **[Lab 08: Git Merge Conflicts](08_git_merge_conflicts.md)** — Practice resolving merge conflicts.
- **[Lab 09: Git Forking](09_git_forking.md)** — Learn how to fork repositories and contribute to other projects.
- **[Lab 10: Git Rebasing](10_git_rebasing.md)** — Rewrite commit history for cleaner, linear project timelines.
- **[Lab 11: Git Cherry-Picking](11_git_cherry_picking.md)** — Selectively merge individual commits.
- **[Lab 12: Git Reset and Git Revert](12_git_reset_and_git_revert.md)** — Undo or revert changes in different ways.
- **[Lab 13: Git Stashing](13_git_stashing.md)** — Temporarily shelve changes without committing.
- **[Lab 14: Git Reflog](14_git_reflog.md)** — Track all actions in your Git repository.
- **[Lab 15: Understanding Git](15_understanding_git.md)** — Deepen your conceptual knowledge of Git internals.
- **[Lab 16: Custom Configurations](16_custom_configurations.md)** — Personalize your Git environment.
- **[Lab 17: Git Troubleshooting](17_git_troubleshooting.md)** — Learn to fix common issues and tricky scenarios.

Feel free to pick and choose topics based on what you need. Each lab builds on the basics you’ve just learned here!


***"An investment in Knowledge pays the best interest" -Ben Franklin***
<br><br>


# What is Git?
![image](https://github.com/user-attachments/assets/7c9e2ab2-33cf-4155-8ecb-1377e791ea54) ![image](https://github.com/user-attachments/assets/f4717836-061d-4094-9ead-a620b2c58b58) ![image](https://github.com/user-attachments/assets/63ca5a7e-825e-402f-a9dc-6cd6fdb8a50e) ![image](https://github.com/user-attachments/assets/588b184e-77e2-4c3a-ae05-6efb8695ae69) ![image](https://github.com/user-attachments/assets/faa90216-e945-4be5-bfbb-1efa19df904b)
 ![image](https://github.com/user-attachments/assets/90336e07-0726-4f0b-8685-4c7e8fabaeef) ![image](https://github.com/user-attachments/assets/e4e80a97-eef4-46a2-95b7-b041944ab292) ![image](https://github.com/user-attachments/assets/6a97cc88-7df1-40cd-9e90-dc494c9340e0)


(photos by: kodekloud.com)

<br><br><br><br>
# Lab 1: Git Setup & Basic Workflows

In this comprehensive lab, you’ll learn how to install and configure Git, then explore its basic day-to-day workflows. By the end, you’ll have a solid foundation for version control with Git.

## Objectives

1. Install Git on Windows, Mac, or Linux.  
2. Configure your Git username and email.  
3. Initialize a new Git repository.  
4. Add, stage, commit, and view commit history.  
5. Learn how to discard uncommitted changes.

## Prerequisites

- A computer running Windows, macOS, or a Linux distribution.
- Basic familiarity with your operating system’s command line or terminal.

---

## I. Install Git

### Windows
- **Option A:** [Download Git for Windows](https://gitforwindows.org/) and run the installer.  
- **Option B (Winget):** Open **Command Prompt** or **PowerShell** and run:
  ```powershell
  winget install --id Git.Git -e --source winget
  ```

### macOS
1. Install [Homebrew](https://brew.sh/) if you don’t have it:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. Install Git using Homebrew:
   ```bash
   brew install git
   ```

### Linux
- **Debian/Ubuntu-based:**
  ```bash
  sudo apt update && sudo apt upgrade
  sudo apt install git git-man
  ```
- **Fedora/CentOS-based:**
  ```bash
  sudo yum install git
  ```
- **Arch-based:**
  ```bash
  sudo pacman -S git
  ```

**Verify Installation:**
```bash
git --version
```
You should see a version number, e.g. `git version 2.x.x`.

---

## II. Configure Git (Global Settings)

1. **Set your name and email** (these appear in your commit metadata):
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

2. **Optional: To get the git bash prompt:
cat << EOF >> ~/.bashrc
```bash
source /usr/share/git-core/contrib/completion/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=true
export GIT_PS1_SHOWUNTRACKEDFILES=true
export PS1='[\u@\h \W$(declare -F __git_ps1 &>/dev/null && __git_ps1 " (%s)")]\$ '
```

3. **Optional: Validate your entries**:
   ```bash
   git config --global --list
   ```
4. **Optional: Edit your Git config**:
   ```bash
   git config --global --edit
   ```
5. **Optional: Unset a config value**:
   ```bash
   git config --global --unset user.name
   ```

---

## III. Initialize Your First Repository

1. Create a new folder for your project:
   ```bash
   mkdir -p Projects/story-blog
   cd Projects/story-blog
   ```
2. Initialize the Git repository:
   ```bash
   git init
   ```
3. **(Optional)** If you already have an existing repo or want to clone one from GitHub:
   ```bash
   git clone https://github.com/githubteacher/example-basic.git
   cd example-basic
   ```

---

## IV. Basic Workflows

### 1. Understanding the Staging Area

- Think of the _staging area_ (also called the _index_) as the “middle ground” between **your working files** and **the final commit** in Git.
- You place changes here to mark them as ready to commit, while leaving other changes out if they aren’t ready yet.

### 2. Create & Stage Your First Files

1. Create a simple file:
   ```bash
   echo "This is a beautiful story" > story1.txt
   echo "A Lion lay asleep in the forest" > lion-and-mouse.txt
   ```
2. Optional step: **Ignore** `story1.txt` in future commits:
   ```bash
   echo "story1.txt" > .gitignore
   ```
3. **Check the status** of your repository to see what’s staged/untracked:
   ```bash
   git status
   ```
4. **Stage your changes**:
   ```bash
   git add .
   ```
   or if you prefer to stage individual files:
   ```bash
   git add lion-and-mouse.txt
   ```

### 3. Commit Your Changes

```bash
git commit -m "Add the lion and mouse story"
```
- The `-m` flag lets you specify a _commit message_ directly.

### 4. Verify Your Commit

```bash
git log
```
or, for a more concise output,
```bash
git log --oneline
```
You should see your commit message, author, and date.

### 5. Make More Changes & Commit Again

1. Create or edit another file (e.g., `notes.md`):
   ```bash
   echo "Some notes about Git" > notes.md
   ```
2. Stage only that file:
   ```bash
   git add notes.md
   ```
3. Commit again:
   ```bash
   git commit -m "Add notes on Git"
   ```

### 6. Discard Uncommitted Changes

- If you’ve edited a file, but **haven’t staged** those changes yet and want to revert:
  ```bash
  git checkout -- <filename>
  ```
  This reverts `<filename>` to the last committed version.

- If changes are **already staged**, you’d need to unstage them first with:
  ```bash
  git reset HEAD <filename>
  ```
  and then discard them using the checkout command.

---

## Summary

- **Installation & Configuration**: You installed Git and set up your username/email.  
- **Repository Initialization**: You created (or cloned) your first Git repository.  
- **Basic Workflows**:  
  - Created files and staged changes.  
  - Committed changes with a message.  
  - Viewed commit history with `git log`.  
  - Learned how to discard uncommitted changes.

These skills form the core of day-to-day Git usage. You’re now ready to explore more advanced topics like branching, merging, and collaboration with remote repositories!

<br><br>

### Next Steps
Move on to [Lab 2: Git Branches](02_git_branches.md) to learn about branches, merging, and collaboration with teams


# Lab 1: Git Setup & Basics

Welcome to **Lab 1**, where you'll learn how to install Git on Windows, Mac, and Linux, configure your global settings, and initialize your first repository.

---

## Objectives

  I. Install Git on your system (Windows, Mac, or Linux). \
 II. Configure your Git username and email. \
III. Initialize a new Git repository. \
 IV. Create your first commit.

---

## Prerequisites

- A computer running Windows, macOS, or a Linux distribution.
- Basic familiarity with your operating system's command line or terminal.

---

## I. Install Git

### Windows
- **Option A:** Use [Git for Windows](https://gitforwindows.org/). Download and run the installer.  
- **Option B (Winget):** Open **Command Prompt** or **PowerShell** and run:  
  ```powershell
  winget install --id Git.Git -e --source winget

### Mac
* Steps:
1) Install `Homebrew` if you don't already have it:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
2) Then, install `Git` using `Homebrew`:
```
brew install git
```

### Linux
- For Debian/Ubuntu-based systems:
```bash
sudo apt-get update
sudo apt-get install git
```

- For Fedora/CentOS-based systems:
```bash
sudo yum install git
```

- For Arch-based systems:
```bash
sudo pacman -S git
```

3. Verify Installation:
```bash
git --version
```
- You should see a version number, e.g. git version 2.x.x.

II. Configure Git Username and Email (IMPORTANT):
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```



5. Initialize Your First Repository
Create a new folder for your project:
bash
Copy
Edit
mkdir my-first-git-repo
cd my-first-git-repo
Initialize the Git repository:
bash
Copy
Edit
git init
Create a simple file:
bash
Copy
Edit
echo "# My First Git Repo" > README.md
Stage and commit:
bash
Copy
Edit
git add README.md
git commit -m "Initial commit"
6. Verify Your Commit
bash
Copy
Edit
git log
You should see your commit message, author, and date. Congratulations—you've made your first commit!

Next Steps
Move on to Lab 2: Basic Workflows to learn about adding, committing, viewing logs, and the staging area in more detail.


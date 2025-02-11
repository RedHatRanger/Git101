# What is Git?
![image](https://github.com/user-attachments/assets/7c9e2ab2-33cf-4155-8ecb-1377e791ea54) ![image](https://github.com/user-attachments/assets/f4717836-061d-4094-9ead-a620b2c58b58) ![image](https://github.com/user-attachments/assets/63ca5a7e-825e-402f-a9dc-6cd6fdb8a50e) ![image](https://github.com/user-attachments/assets/588b184e-77e2-4c3a-ae05-6efb8695ae69) ![image](https://github.com/user-attachments/assets/faa90216-e945-4be5-bfbb-1efa19df904b)
 ![image](https://github.com/user-attachments/assets/90336e07-0726-4f0b-8685-4c7e8fabaeef)


(photos by: kodekloud.com)

<br><br><br><br>
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

<br><br><br><br>

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
sudo apt update && sudo apt upgrade
sudo apt install git git-man
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

## II. Configure Git Username and Email (IMPORTANT):
```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```



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

## IV. Create Your First Commit
3. Create a simple file:
```bash
echo "This is a beautiful story" > story1.txt
````

4. Stage and commit:
```bash
git add .
git commit -m "Initial commit"
```

6. Verify Your Commit
```bash
git log
```
OR
```
git log --oneline
```
OR
```
git status
```

### You should see your commit message, author, and date. Congratulations—you've made your first commit!

<br><br>

### Next Steps
Move on to [Lab 2: Basic Workflows](02_basic_workflows.md) to learn about adding, committing, viewing logs, and the staging area in more detail.


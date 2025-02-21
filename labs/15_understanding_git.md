***"The only way to learn a new programming language is by writing programs in it." – Dennis Ritchie***
<br><br>

# Lab 15: 🏆 Understanding Git 🚀 (5th Grader Edition)

![image](https://github.com/user-attachments/assets/0921076a-76b1-4154-a5a2-64f4f25c479a)
![image](https://github.com/user-attachments/assets/ce296839-7487-4e7b-a9d6-18e74699874e)
![image](https://github.com/user-attachments/assets/64cf17a3-a5be-43c0-8533-4648f12e9592)

<br><br>
>The 1st two letters of the hash are used as the key, and this is the folder where hash is stored.
![image](https://github.com/user-attachments/assets/d832be97-afe9-4f78-9014-5e5273b83925)


![image](https://github.com/user-attachments/assets/8869d82a-736d-4f47-923e-8f2581ab9496)

<br><br>
>We can pretty print with the cat-file, and only the 1st five characters of the hash are needed.
![image](https://github.com/user-attachments/assets/29c2e4bc-6dc1-4924-a227-2f1cb71d9ffc)

<br><br>
>You can also cat-file the commit hash.
![image](https://github.com/user-attachments/assets/92de275b-270b-423e-a8f6-65460f248e3c)


## Main Lab
Welcome to the **Understanding Git Lab!** Today, we’ll learn how Git stores your work and how we can peek inside Git’s secret folders! 🤩

---

## 🎯 What You’ll Learn
- How Git saves your work
- What Git’s secret `.git` folder does
- The difference between Git's **porcelain** (easy commands) and **under-the-hood plumbing** commands
- How to see hidden Git files

---

## 🏗️ Step 1: Create Your Own Git Project
1. Open **Git Bash** (or Terminal if you're using Linux/Mac).
2. Pick a folder to work in and type:
   ```bash
   mkdir my-git-lab && cd my-git-lab
   git init
   ```
   - This creates a new Git project in a folder called `my-git-lab`.

3. Check what Git created:
   ```bash
   ls -la .git
   ```

---

## 🔎 Step 2: Add a File and See What Happens
1. Make a new file:
   ```bash
   echo "Hello Git!" > hello.txt
   git add hello.txt
   git commit -m "First commit!"
   ```
2. Run the following to see your commit:
   ```bash
   git log --oneline
   ```

---

## 🛠️ Step 3: Porcelain vs. Plumbing Commands
Git has two types of commands:
- **Porcelain commands** (user-friendly, everyday commands):
  ```bash
  git status
  git add
  git commit
  git log
  git push
  ```
- **Under-the-Hood (Plumbing) commands** (low-level, internal Git mechanics):
  ```bash
  git hash-object  # Turns a file into a Git object
  git cat-file     # Reads raw Git objects
  git ls-tree      # Shows tree objects
  git rev-parse    # Converts references into hash IDs
  git update-ref   # Manually updates references
  git show-ref     # Lists all references
  git reflog       # Shows history of branch movements
  git for-each-ref # Lists and formats references
  git verify-pack  # Inspects packed Git objects
  git check-ref-format # Checks if a branch name is valid
  git mktree       # Creates a new tree object
  git pack-objects # Combines loose objects into a pack
  git write-tree   # Writes the staging area to a tree
  git unpack-objects # Unpacks Git objects
  git update-index # Manually updates the index
  ```

### 🎮 Deep Dive into `reflog` and `cat-file`

#### 🔄 **Time Traveling with `git reflog`**
Think of `git reflog` as Git’s time machine! Every time you switch branches, make a commit, or reset something, Git logs these actions. If you ever lose a commit, `git reflog` can help you bring it back!

**Example:** Recovering a lost commit
```bash
git reflog
```
**Output:**
```
abc1234 HEAD@{0}: commit: Added new feature
xyz5678 HEAD@{1}: reset: moving to previous commit
```
Oops! You accidentally reset a commit! No worries, just restore it:
```bash
git reset --hard abc1234
```
Now your lost commit is back! 🚀

#### 🕵️‍♂️ **Investigating Git Objects with `git cat-file`**
This command lets you open and inspect Git objects (commits, blobs, and trees). Think of it as **opening a secret Git vault!**

**Example:** Viewing a commit object
```bash
git log --oneline
```
**Output:**
```
abc1234 First commit!
```
Now, inspect this commit:
```bash
git cat-file -p abc1234
```
**Output:**
```
tree 9d1e76b
parent d3b0738
author John Smith <john@example.com>
committer John Smith <john@example.com>

First commit!
```
This tells us:
- The **tree ID** (which holds the files in the commit)
- The **parent commit** (if it’s not the first one)
- The **author and committer** (who created it and when)
- The **commit message**

**Example:** Viewing a file stored inside Git
```bash
git cat-file -p 9d1e76b
```
This shows the **tree structure**, revealing files in the commit. You can then inspect individual files stored in Git!

---

## 🕵️‍♂️ Step 4: Look Inside Git’s Object Storage
1. Run:
   ```bash
   ls .git/objects
   ```

---

## 🎉 You Did It!
You just explored Git’s hidden world! 🌎 Now you know how Git stores your work like a superhero with secret codes!

🚀 **Challenge:** Try adding more files and checking how they’re stored!



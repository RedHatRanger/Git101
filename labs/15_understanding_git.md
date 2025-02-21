***"The only way to learn a new programming language is by writing programs in it." – Dennis Ritchie***
<br><br>

# Lab 15: 🏆 Understanding Git 🚀 (5th Grader Edition)

>Porcelain vs. Plumbing Commands
![image](https://github.com/user-attachments/assets/0921076a-76b1-4154-a5a2-64f4f25c479a)

<br><br>
>Let's explore one of the Plumbing Commands, `hash-object`: \
![image](https://github.com/user-attachments/assets/64cf17a3-a5be-43c0-8533-4648f12e9592)
![image](https://github.com/user-attachments/assets/d832be97-afe9-4f78-9014-5e5273b83925)
>The 1st two letters of the hash are used as the key, and this is the folder where hash is stored.
![image](https://github.com/user-attachments/assets/8869d82a-736d-4f47-923e-8f2581ab9496)

<br><br>
>We can pretty print with the cat-file, and only the 1st five characters of the hash are needed.
![image](https://github.com/user-attachments/assets/29c2e4bc-6dc1-4924-a227-2f1cb71d9ffc)

<br><br>
>You can also cat-file the commit hash.
![image](https://github.com/user-attachments/assets/92de275b-270b-423e-a8f6-65460f248e3c)

<br><br>
## Main Lab
Welcome to the **Understanding Git Lab Series!** Today, we’ll break Git into smaller, hands-on labs to help you explore how Git stores your work and how we can peek inside Git’s secret folders! 🤩

---

## 🎯 What You’ll Learn

- How Git saves your work
- What Git’s secret `.git` folder does
- The difference between Git's **porcelain** (easy commands) and **under-the-hood plumbing** commands
- How to see hidden Git files

---

<br><br>
# 🕵️‍♂️ Mini-Lab 1: Setting Up Your Git Project

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

<br><br>
# 🕵️‍♂️ Mini-Lab 2: Understanding Git Storage with `git hash-object`

## 🛠️ Storing a File in Git

Git stores files in a unique way using **SHA-1 hashes**. Let's try it out!

### Why Use `git hash-object -w`?

Normally, when you use `git add`, Git tracks files inside a **staging area** before committing them. However, sometimes you might want to **store a file in Git’s object database without adding it to a commit**. This is where `git hash-object -w` comes in!

By running this command, you manually tell Git:

1. "Take this file, compress it, and save it inside `.git/objects`."
2. "Return a unique hash for this file so I can reference it later."

### 🏗️ Try It Out!

1. Run this command to store `README.md` as a Git object:

   ```bash
   git hash-object -w README.md
   ```

   **Output:**

   ```
   a62c352299dbba73f7e1cc95499bb0cb1bdd6640
   ```

   - This hash is Git’s unique way of identifying this exact file.
   - Git has now stored `README.md` inside the `.git/objects` folder **even though it’s not part of a commit yet**.

2. Now, inspect the contents using `git cat-file`:

   ```bash
   git cat-file -p a62c352299dbba73f7e1cc95499bb0cb1bdd6640
   ```

   - This command retrieves and prints the exact contents of the stored file.

### Why Is This Useful?

- You can store files in Git without committing them.
- If you store a file and later run `git add`, Git **won't create a duplicate** – it recognizes the same content!
- Useful for **testing, debugging, and understanding how Git stores objects under the hood**.

---

<br><br>
# 🕵️‍♂️ Mini-Lab 3: Deep Dive into `reflog` and `cat-file`

## 🔄 🚗⏳Time Traveling with `git reflog`

Think of `git reflog` as Git’s time machine! If you ever lose a commit, `git reflog` can help you bring it back!

**Example:** Recovering a lost commit

```bash
git reflog
```

**Output:**

```
abc1234 HEAD@{0}: commit: Added new feature
xyz5678 HEAD@{1}: reset: moving to previous commit
```

Now, let’s say you want to go back to the commit with **abc1234**, but your project is in a broken state. You can **reset everything to that exact moment** by running:

```bash
git reset --hard abc1234
```

🚨 **Why not reset to `xyz5678`?**

- `xyz5678` represents a **reset action**, meaning you already moved backward to a previous commit.
- If you reset to `xyz5678`, you'd just be keeping the rollback state without restoring the lost commit.
- Resetting to `abc1234` brings back the actual work you want!

🚨 **Warning!** `--hard` means **everything in your working directory will change** to match that commit. If you had uncommitted changes, they will be **lost** forever! Use it only when you're sure.

🔄 If you don’t want to lose changes but still move to an earlier commit, try:

```bash
git reset --soft abc1234
```

This keeps your changes but resets Git’s history to that commit!

<br><br>
## 🕵️‍♂️ Mini-Lab 4: Investigating Git Objects with `git cat-file`

This command lets you open and inspect Git objects (commits, blobs, and trees).

**Example:** Viewing a commit object

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

---

<br><br>
## Congratulations🎉!  You Did It!

You just explored Git’s hidden world! 🌎 Now you know how Git stores your work like a superhero with secret codes!

🚀 **Challenge:** Try adding more files and checking how they’re stored!

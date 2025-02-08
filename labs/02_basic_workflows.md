# Lab 2: Basic Workflows

In **Lab 2**, we’ll build on the basics by exploring the typical Git workflow—adding, staging, committing, and viewing commit history in more depth.

---

## Objectives

  I. Understand how the staging area works \
 II. Add and commit changes effectively \
III. Explore your project commit history using `git log` \
 IV. Learn how to discard uncommitted changes

<br><br><br><br>

## I. Understanding the Staging Area

- **Option A: Using an Existing Repo:**  
  If you have an existing repository from **Lab 1**, simply navigate to that folder.

- **Option B: Clone a GitHub Repo:**  
  Clone a sample repository from GitHub:
  ```bash
  git clone https://github.com/githubteacher/example-basic.git
  cd example-basic
  ```

## II. Add and commit changes effectively
1. Create or edit a file (e.g., notes.md):
```bash
echo "Some notes about Git" > notes.md
```

2. Check the status of your repository:
```bash
git status
```

3. Stage your changes:
```bash
git add notes.md
```
OR
```
git add .
```

4. Commit your changes:
```bash
git commit -m "Add notes on Git"
```

## III. Explore your project commit history:
```bash
git log --oneline
```

## IV. Discard uncommitted changes
>The staging area (also called the index) is where Git tracks changes you intend to include in the next commit.
>Practice adding changes to multiple files, then running git status to see which are staged vs. unstaged.

5. Discarding Changes (Unstaged)
If you edited a file and want to revert it (before staging):
```bash
git checkout -- <filename>
```
>This reverts the file to the last committed version.

<br><br>
## Summary
You now understand how to make, stage, and commit changes, plus inspect and discard uncommitted changes. These operations form the core of day-to-day Git usage.

Next: Lab 3: Branching Essentials

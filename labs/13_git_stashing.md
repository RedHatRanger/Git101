***"Neither comprehension nor learning can take place in an atmosphere of anxiety." – Rose Kennedy***
<br><br>

# Lab 13: Git Stashing (5th Grader Edition)

## Quick Review of Previous Labs
- **Lab 1**: We set up Git and saved our first files.
- **Lab 2**: We created branches to safely try new ideas.
- **Lab 3**: We merged those branches back into the main code.
- **Lab 4**: We learned to push our work to a remote and pull updates.
- **Lab 5**: We cloned a remote repo onto our computer.
- **Lab 6**: We made Pull Requests so others could review or approve our changes.
- **Lab 7**: We fetched and pulled updates to stay in sync.
- **Lab 8**: We fixed merge conflicts when two people changed the same line.
- **Lab 9**: We forked a repository to make our own copy.
- **Lab 10**: We rebased to rearrange or squash commits.
- **Lab 11**: We cherry-picked a single commit from another branch.
- **Lab 12**: We reset or reverted mistakes to keep our history clean.

**Now**, in **Lab 13**, we’ll learn about **stashing**. Sometimes you need to pause your work and switch tasks. **Stash** saves your current changes away without committing them, so you can come back later.

---

## Why Use Stash?
**Stashing** is like **putting your half-finished homework into a safe** so you can help a friend with something else. Later, you can open that safe and continue exactly where you left off!

---

## Stashing (How-to)

1. **Overview**

![image](https://github.com/user-attachments/assets/d5b25b33-fe77-4c07-bb3a-b0220abe0d27)

   This image shows the basic idea of stashing.

2. **Stash to Stash Area**

![image](https://github.com/user-attachments/assets/4f1ecb72-00b1-4104-8dcd-38bf389dc37c)

   Temporarily move your files from the staging area (or working directory) into the “stash” so they aren’t committed yet.

3. **Get Changes Back**

![image](https://github.com/user-attachments/assets/cd912a14-ef90-4c87-9116-ee01297923ab)

   You can **pop** or **apply** the stash to restore your changes.

4. **Stashing = Storing Books**

![image](https://github.com/user-attachments/assets/4107c74f-319e-4a1e-8973-c222c9d92f08)

   Think of a stash like a **library shelf**. You check out your changes later when you need them.

5. **View Everything in Stash**

![image](https://github.com/user-attachments/assets/0fc05788-a73b-460f-9794-f4b38afde4d1)

   `git stash list` shows all stashes, like a list of library books you have.

6. **Pop a Specific Stash**

![image](https://github.com/user-attachments/assets/b9dadebc-6b56-4001-90d5-9990d89d2cb2)

   `git stash pop stash@{2}` (for example) brings back that one stash.

---

## Main Lab

### 1. Stash Changes and Switch Tasks
Suppose Sarah is editing `frogs-and-ox.txt` but needs to jump to `master` to fix a typo. She can:
```bash
# Save uncommitted changes in a stash:
git stash

git stash list  # See what's in the stash

# Switch to main:
git checkout main
# Fix the typo in lion-and-mouse.txt, then commit.
```

Now her `frogs-and-ox` edits are safely stashed.

### 2. Apply (Pop) the Stash
After fixing the typo, Sarah goes back to `story/frogs-and-ox`:
```bash
git checkout story/frogs-and-ox

git stash list
# Maybe there's stash@{0}, stash@{1}, etc.

git stash pop stash@{0}
# or just 'git stash pop' for the newest stash.
```
This moves the stashed changes back into her working files.

### 3. See What’s in Each Stash
```bash
git stash show stash@{0}
git stash show stash@{1}
```
This tells you which files are in each stash. For example, you might see `story3.txt` or `story2.txt` was stashed.

### 4. Stash Multiple Sets of Changes
You can stash multiple times if you’re juggling different tasks. Just remember to `pop` or `apply` them when you’re ready to continue.

---

## Summary
1. **git stash**: Temporarily stores your uncommitted changes so you can switch tasks.
2. **git stash pop** or **apply**: Brings back those changes.
3. **git stash list**: Shows all your stashed snapshots.
4. **git stash show**: Tells you what’s inside each stash.

Stashing is like **bookmarking** your current progress so you can help someone else or fix a quick bug, then get right back to where you were. **Awesome job** learning to stash!

---

**Next**: [Lab 14: Git Reflog](14_git_reflog.md)

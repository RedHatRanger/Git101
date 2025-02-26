***“You miss 100% of the shots you don’t take.” – Wayne Gretzky (or Michael Scott)***
<br><br>

# Lab 14: Git Reflog (5th Grader Edition)

![image](https://github.com/user-attachments/assets/2a586b67-a6f2-4f80-b397-3c4760fd0b51) 
![image](https://github.com/user-attachments/assets/21ec10cf-52a4-4bfc-ad3b-9d6fe1af234f) 
![image](https://github.com/user-attachments/assets/331f4d39-7c18-4379-b31b-d066fbde9bd4) 
![image](https://github.com/user-attachments/assets/ae15b2b8-973b-4dff-ab99-2a459262f864)
![image](https://github.com/user-attachments/assets/8292ea61-6435-4ba3-96d5-95657f20b83d)
![image](https://github.com/user-attachments/assets/f742cde3-d8b6-42f4-93f2-dec9720ea677)

<br><br>
## Quick Review of Previous Labs
- **Lab 1**: We set up Git and saved our first files.
- **Lab 2**: We created branches to work on stories without messing up the main code.
- **Lab 3**: We merged those branches back in.
- **Lab 4**: We learned to push to a remote and pull updates.
- **Lab 5**: We cloned a remote repo to our computer.
- **Lab 6**: We used Pull Requests for sharing code.
- **Lab 7**: We fetched and pulled new changes.
- **Lab 8**: We handled merge conflicts.
- **Lab 9**: We forked a project.
- **Lab 10**: We rebased to fix commit history.
- **Lab 11**: We cherry-picked single commits.
- **Lab 12**: We reset or reverted commits we didn’t want.
- **Lab 13**: We stashed changes to save them for later.

**Now**, in **Lab 14**, we’ll explore **git reflog**. Sometimes you make a big mistake—maybe you reset too far back—and you think all is lost. But **reflog** can help you find your way back!

---

<br><br>
## Why Use Reflog?
**Reflog** stands for “Reference Log.” It’s like your personal timeline of **all** the moves your `HEAD` has made—even commits you thought you erased. If you do a hard reset, or revert, and want to undo that, the reflog can show you old commit IDs.

Think of **reflog** as a detective’s notebook of **every** move your code made.

---

<br><br>
## Setup Procedure
We’ll create a few commits, then do some resets, so we have “lost” commits that we can recover with reflog.

1. **Start on Main**:
   ```bash
   cd ~/story-blog
   git checkout main
   ```
   Make sure your `main` branch is up to date.

2. **Add a New File** (`milkmaid-and-her-pail.txt` for example):
   ```bash
   cat << EOF > milkmaid-and-her-pail.txt
   --------------------------------------------
          THE MILKMAID AND HER PAIL
   --------------------------------------------
   A Milkmaid was carrying her pail of milk.
   She daydreamed about the money from selling the milk,
   buying chickens, making more money... until she tripped,
   and the milk spilled, ending her dreams.
   EOF

   git add milkmaid-and-her-pail.txt
   git commit -m "Add milkmaid story"
   git push -u origin main
   ```

3. **Make Another Commit**:
   ```bash
   echo "Moral: Don’t count your chickens before they hatch." >> milkmaid-and-her-pail.txt
   git add milkmaid-and-her-pail.txt
   git commit -m "Add moral to milkmaid story"
   git push
   ```

4. **Perform a Hard Reset** (Pretend you made a mistake!):
   ```bash
   git reset --hard HEAD~1
   # Oops, we removed the moral from the story!
   ```
   Now we’ve “lost” that commit in our normal history, but we can still find it with reflog.

---

<br><br>
## Main Lab

### 1. View Your Reflog
```bash
git reflog
```
You’ll see a timeline of moves—commits, resets, checkouts. Even the commit you “lost” is there!

> **Kid-Friendly**: This is your secret diary of every big step you took, even if you tried to erase it.

### 2. Find the Commit You Want
Look for the line that says “Add moral to milkmaid story.” It might say something like:
```
abcdef1 HEAD@{3}: commit: Add moral to milkmaid story
```
That **abcdef1** (hash) is the commit we want.

### 3. Bring That Commit Back
You could **checkout** or **cherry-pick** that commit hash. For example:
```bash
git cherry-pick abcdef1
```
Now you have your moral line again!

### 4. Keep Exploring
Try doing a few more resets or commits, then run `git reflog` to see all your moves. Notice that even after a **hard reset** you can still find the old commits in reflog for a while.

---

## Summary
1. **Reflog** shows every move—commits, resets, checkouts.
2. You can find “lost” commits by checking the reflog for their hashes.
3. **Recovery**: Use `git cherry-pick <hash>` or `git checkout <hash>` to get your code back.

That’s **Git Reflog**—your secret detective record of all changes. Good job learning how to dig up commits you thought were gone!

---

**Next**: [Lab 15: Understanding Git Internals](15_understanding_git.md)





# Lab 12: Git Reset and Git Revert
![image](https://github.com/user-attachments/assets/1f07ffc7-5613-4eb5-b086-46b66e033f26) 




![image](https://github.com/user-attachments/assets/44da4c30-7418-4523-b3d7-d3bd434f45dc)
>We can still see the changes that were made with git status with a soft reset.

![image](https://github.com/user-attachments/assets/ad752b2d-3965-4a5b-84e3-cae50a630554)
>But if we reset with the hard reset, the commit will be reset without saving all those changes.

![image](https://github.com/user-attachments/assets/71414a14-c1fb-4d07-ba24-d7d16e00b3cb)
>The 3rd story file is now completely gone.

<br><br>
# Main Lab

<br><br>
1. Let's find out how many stories sarah altered in that last commit (Quiz Question #1):
![image](https://github.com/user-attachments/assets/fe458c71-11cc-43d4-b007-d342d65b8233)
```
git log --name-only
```
![image](https://github.com/user-attachments/assets/bd78f2e0-403b-400b-901e-0e092e79f84d)
>Sarah altered 5 stories

<br><br>
2. Help Sarah undo all the changes made in that last commit:
![image](https://github.com/user-attachments/assets/766f7633-302a-4154-b074-98a098fd48ac)
```
git revert HEAD~0

# OR
# git revert <commit_id>
```
![image](https://github.com/user-attachments/assets/6a930706-8e72-4a73-ad65-0a0f9a99c433)

<br><br>
3. Quiz Question #2:
![image](https://github.com/user-attachments/assets/b9284fd7-bc78-47e2-b334-74e90a24c347)
>Answer: --soft

<br><br>
4. Quiz Question #3:
![image](https://github.com/user-attachments/assets/ae45a6e4-e1ad-4d90-a6d1-2391d8ae7c70)
>Answer: --hard

<br><br>
5. Help Sarah revert the last commit but retain the unfinished changes so she can finish her story:
![image](https://github.com/user-attachments/assets/10869d0a-a456-4945-af35-f6bc9c539581)
```
git reset --soft HEAD~1
git add hare-and-tortoise.txt
git commit -m "Finished hare-and-tortoise story"
```

<br><br>
6. Quiz Question #4:
![image](https://github.com/user-attachments/assets/7192bb72-8de9-46c2-a77c-40378fba00cf)

![image](https://github.com/user-attachments/assets/e598660a-ea21-414b-80d8-f98c078f80eb)
>Answer: There have been 3 commits since Sarah finshed her story.

<br><br>
7. Help Sarah reset her story to the previous good version of the story (since 'Finished hare-and-tortoise story'):
![image](https://github.com/user-attachments/assets/1190c05d-7f97-46b9-ae80-693f326a0d56)
```
git reset --hard HEAD~3
```
![image](https://github.com/user-attachments/assets/63947dd5-0f52-4926-ba72-dc91c6db63c6)

* Done



















***"One big reason for a winning attitude is that you will take the necessary steps and not quit when the going gets difficult." – Don M.Green***
<br><br>

# Lab 12: Git Reset and Git Revert (5th Grader Edition)

![image](https://github.com/user-attachments/assets/50af2764-d831-4198-ab23-2b646ccb7118)
![image](https://github.com/user-attachments/assets/1f07ffc7-5613-4eb5-b086-46b66e033f26)
>This will delete the story but create a new commit.
<br><br>

![image](https://github.com/user-attachments/assets/dc9524da-362f-4449-8f47-dc7b97d07af4)
>The soft reset will let you keep all the changes you made.

![image](https://github.com/user-attachments/assets/44da4c30-7418-4523-b3d7-d3bd434f45dc)
![image](https://github.com/user-attachments/assets/ad752b2d-3965-4a5b-84e3-cae50a630554)
![image](https://github.com/user-attachments/assets/71414a14-c1fb-4d07-ba24-d7d16e00b3cb)

## Quick Review of Previous Labs
- **Lab 1**: We set up Git and saved our very first files.
- **Lab 2**: Made branches so we could safely try new ideas.
- **Lab 3**: Merged branches back into the main code.
- **Lab 4**: Learned to push our work to a remote (like GitHub) and pull updates.
- **Lab 5**: Cloned a remote repo onto our computer.
- **Lab 6**: Created Pull Requests so others could approve or review our changes.
- **Lab 7**: Fetched and pulled to keep up with the latest changes.
- **Lab 8**: Solved merge conflicts when two people changed the same line.
- **Lab 9**: Forked a repository, making our own copy to experiment with.
- **Lab 10**: Used **rebase** to rearrange or squash commits.
- **Lab 11**: **Cherry-picked** a single commit from another branch.

**Now**, in **Lab 12**, we’ll learn how to **undo** changes using **git reset** and **git revert**. Sometimes you make a mistake, or want to travel back in time to fix something—these commands help you do that.

---

## Why Reset or Revert?
- **Reset**: Moves your project back to a previous point, like turning back pages in a story and erasing what happened after that.
- **Revert**: Creates a new commit that **undoes** a previous commit, but keeps history intact.

Think of **reset** as traveling back in time and rewriting events, while **revert** is adding a new event that cancels the old mistake.

---

## Main Lab

### 1. Checking How Many Stories Sarah Changed (Quiz #1)

If we do:
```bash
git log --name-only
```
We can see which files changed in each commit. Sarah changed **5** stories in her last commit.

>Explanation: This is like reading the pages in Sarah’s last update to see how many story titles she touched.

---

### 2. Undo the Last Commit with Revert

```bash
git revert HEAD~0
# or: git revert <commit_id>
```

This creates a **new** commit that undoes the changes in the last commit. It’s like writing another page that says, “Oops, that last change was a mistake.”

>Explanation: You’re not erasing the old page, you’re adding a page on top that says, “Ignore the previous page!”

---

### 3. Soft Reset vs Hard Reset (Quiz #2 & #3)

- **`--soft`** reset: We move back, but we keep the changes in our working files (just not committed). So you can still fix them and commit again.
- **`--hard`** reset: We move back, and we **lose** the changes entirely (like they never happened).

#### Example
```bash
git reset --soft HEAD~1
# Moves the pointer back one commit, but keeps the changes.

git reset --hard HEAD~3
# Moves back three commits and discards all changes.
```

> **Kid-Friendly**: **Soft** reset is like stepping back in the story but saving your notes. **Hard** reset is throwing away the new pages you wrote.

---

### 4. Revert the Last Commit but Keep Changes?

Sometimes you want to revert a commit but continue working on those changes. You can do something like a **soft** reset first:
```bash
git reset --soft HEAD~1
# This way, you still have the changes as uncommitted edits.

# Then you can fix them up and commit again:
git add hare-and-tortoise.txt
git commit -m "Finished hare-and-tortoise story"
```

Now you can keep editing without fully erasing your work.

---

### 5. Reset to a Previous “Good” Commit

If Sarah wants to jump back to how it was **3 commits ago**:
```bash
git reset --hard HEAD~3
```

This basically says, “Tear out the last 3 pages and pretend they never existed.” **Poof**, all changes from those 3 commits vanish.

---

## Summary
1. **Revert** adds a new commit that undoes a previous commit, preserving history.
2. **Reset** moves your branch pointer back in time.
   - **Soft**: Keep your local changes.
   - **Hard**: Erase them entirely.
3. Use them carefully when you need to fix a big mistake or rewrite your last commits.

**Great job** learning how to travel back in Git’s timeline to fix or erase mistakes! Now you can keep your story squeaky clean.

---

**Next**: [Lab 13: Git Stashing](13_git_stashing.md)

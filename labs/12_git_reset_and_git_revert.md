***"One big reason for a winning attitude is that you will take the necessary steps and not quit when the going gets difficult." – Don M.Green***
<br><br>

# Lab 12: Git Reset and Git Revert (5th Grader Edition)

### Samples
>This will delete the third story but create a new commit. 
![image](https://github.com/user-attachments/assets/1f07ffc7-5613-4eb5-b086-46b66e033f26)

<br><br>
>However, a `git reset --soft <commit-id>` or `git reset --soft HEAD~1` will let you keep the file and all the changes you made.
![image](https://github.com/user-attachments/assets/dc9524da-362f-4449-8f47-dc7b97d07af4)

<br><br>
>But if we reset with the hard reset, the commit will be reset without saving all those changes, and the file(s) will be lost in time!
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

**Now**, in **Lab 12**, we’ll learn how to **undo** changes using **git reset** and **git revert**. Sometimes you make a mistake, or want to travel back in time to fix something!

---

## Why Reset or Revert?
- **Reset**: Moves your project back to a previous point, like turning back pages in a story and erasing what happened after that.
- **Revert**: Creates a new commit that **undoes** a previous commit, but keeps history intact.

Think of **reset** as traveling back in time and rewriting events, while **revert** is adding a new event that cancels the old mistake.

---

## Lab Setup:
## Lab Setup
To practice resets and reverts, let’s create a few commits:

1. **Add a new story** on `main`:

   ```bash
   cd ~/story-blog
   git checkout main

   cat << EOF > goose-and-golden-eggs.txt
   --------------------------------------------
         THE GOOSE THAT LAID GOLDEN EGGS
   --------------------------------------------

   Once a man had a Goose that laid him a golden egg every day.
   He grew rich and greedy.
   "If I cut open the Goose, I can get all the eggs at once," he thought.
   But when he did, there were no eggs inside, and the Goose was gone.
   EOF

   git add goose-and-golden-eggs.txt
   git commit -m "Add goose-and-golden-eggs story"
   git push -u origin main
   ```

   Now we have one commit about this “third story.”

2. **Make another commit** changing the Goose story:

   ```bash
   echo "Moral: Greed often overreaches itself." >> goose-and-golden-eggs.txt
   git add goose-and-golden-eggs.txt
   git commit -m "Add moral to goose story"
   git push
   ```

   Now we have multiple commits that we can reset or revert.

3. **Optionally**: Make one more commit for even more practice.

With these commits in place, we can demonstrate how to revert or reset to earlier points.

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
Quiz Question #2:
![image](https://github.com/user-attachments/assets/b9284fd7-bc78-47e2-b334-74e90a24c347)
>Answer: --soft

Quiz Question #3:
![image](https://github.com/user-attachments/assets/ae45a6e4-e1ad-4d90-a6d1-2391d8ae7c70)
>Answer: --hard

>Explanation:
>**`--soft`** reset: We move back, but we keep the changes in our working files (just not committed). So you can still fix them and commit again.
>**`--hard`** reset: We move back, and we **lose** the changes entirely (like they never happened).

#### Example
```bash
git reset --soft HEAD~1
# Moves the pointer back one commit, but keeps the changes.

git reset --hard HEAD~3
# Moves back three commits and discards all changes.
```

>Explanation: **Soft** reset is like stepping back in the story but saving your notes. **Hard** reset is throwing away the new pages you wrote.

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

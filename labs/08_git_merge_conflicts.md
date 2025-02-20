
2. 

>This error states that there is work on the remote repository that doesn't exist locally yet.

<br><br>
3. So we have to do a `git pull origin master` or `git pull` but the conflict is there:
![image](https://github.com/user-attachments/assets/2e7b38ac-ffab-459c-98b0-a5147e7ad320)

![image](https://github.com/user-attachments/assets/017e138a-9b77-4c54-ba07-0e5063c969f0)

```
git log origin/master

# Sarah had the last commit
```
![image](https://github.com/user-attachments/assets/d7de0dc3-d009-44c5-9372-96042215d785)
![image](https://github.com/user-attachments/assets/f4f1ed9f-8aaf-4bee-825b-18a7b60fc43b)

```
cat story-index.txt
```
![image](https://github.com/user-attachments/assets/38fef64a-6336-4e82-830e-73cb2fc3f9d4)
![image](https://github.com/user-attachments/assets/2cbdd58f-990f-43d3-8317-9af667845670)
![image](https://github.com/user-attachments/assets/b6bb338b-9b0a-450b-a5d8-816b7272686c)

<br><br>
4. Modify the `story-index.txt` file:
```
cat << EOF > story-index.txt
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF

git add story-index.txt 
git commit -m "Resolved merge conflicts and merged story index"
git push -u origin master

# The conflicts are resolved!
```
![image](https://github.com/user-attachments/assets/04345d72-720a-45b1-86a5-ab12572751c4)















***"Success is not final, failure is not fatal: it is the courage to continue that counts." – Winston Churchill***
<br><br>

# Lab 8: Merge Conflicts (5th Grader Edition)

![image](https://github.com/user-attachments/assets/a3567edb-a5e0-463e-87b2-004d63f36cb5)
![image](https://github.com/user-attachments/assets/5dabbc9b-c649-4d1f-bc39-ba0006894d6b)
![image](https://github.com/user-attachments/assets/b5e8d250-02c1-4e8d-a9ee-e903cd1a775f)
![image](https://github.com/user-attachments/assets/1890c30f-8c7d-4df1-bea5-270480e81087)
![image](https://github.com/user-attachments/assets/ed28c5f3-b80c-4982-9912-1fb79f494fb7)
![image](https://github.com/user-attachments/assets/61d4b61a-5fdb-483d-b4de-aad91ada02c9)

## Quick Review of Previous Labs
- **Lab 1**: We set up Git and saved our first files (commits).
- **Lab 2**: We created branches so we could work on new stories without breaking the main code.
- **Lab 3**: We merged those branches back into the main code.
- **Lab 4**: We pushed our project to a remote and learned to pull.
- **Lab 5**: We cloned a remote project onto our computer.
- **Lab 6**: We made Pull Requests so others could review our changes.
- **Lab 7**: We fetched and pulled to get updates from the remote.

Now, in **Lab 8**, we face the tricky part: **merge conflicts**. Sometimes two people change the same line, and Git isn’t sure whose change to keep. Let’s see how we fix it!

---

## The Setup

### Max Creates `story-index.txt`
```bash
cd ~/story-blog
cat << EOF > story-index.txt
1. The Lion and the Mooose
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF
```

(The file says "Mooose" with three o’s—maybe that’s a clue!)

---

## Main Lab

### 1. Max Commits the New `story-index.txt`
```bash
git add story-index.txt

git commit -m "Add index of stories"
```

### 2. Pushing Changes Gets Rejected
```bash
git push -u origin master
```

Git says there’s new stuff on the remote that we don’t have yet. So we need to **pull**.

> **Kid Friendly Explanation**: The remote has changes from someone else that your computer doesn’t see yet. You can’t push your changes on top of it without checking those new changes first.

---

### 3. Pulling Causes a Conflict

```bash
git pull origin master
```

You might see messages like:

```
Auto-merging story-index.txt
CONFLICT (content): Merge conflict in story-index.txt
```

Git is confused because **Sarah** changed `story-index.txt` on the remote, and **Max** changed it too.

> **Why a Conflict?** Think of it like two kids writing different words on **the same line** of a story. Git can’t guess what the final line should say.

### 4. Checking Logs and the Conflict

```bash
git log origin/master
# It shows Sarah had the last commit.

cat story-index.txt
# You might see conflict markers.
```

Example of conflict markers:
```
<<<<<<<< HEAD
1. The Lion and the Mooose
=======
1. The Lion and the Mouse
>>>>>>> origin/master
2. The Frogs and the Ox
3. The Fox and the Grapes
...
```

That means Git is showing you both versions: **Max’s** (`HEAD`) and **Sarah’s** (`origin/master`).

---

### 5. Fix the File, Then Commit

Max decides to correct the spelling and keep Sarah’s version:

```bash
cat << EOF > story-index.txt
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF

git add story-index.txt

git commit -m "Resolved merge conflicts and merged story index"

git push -u origin master
```

No more conflict!

> You erased the confusing parts and wrote down the correct line. You told Git, “This is how I want the final file to look.”

---

## Summary
1. **Conflict**: When two people change the same line, Git doesn’t know which is right.
2. **Fix**: You open the file, remove the conflict markers, and keep the correct text.
3. **Commit**: After editing, you commit again to tell Git, “All done.”

Now you know how to handle merge conflicts: pick the correct lines, remove the markers, and commit. Great job!

---

**Next**: [Lab 9: Git Forking](09_git_forking.md)




































# Lab 8: Merge Conflicts (5th Grader Edition)

> ***"Success is not final, failure is not fatal: it is the courage to continue that counts."*** – Winston Churchill

![image](https://github.com/user-attachments/assets/a3567edb-a5e0-463e-87b2-004d63f36cb5)
![image](https://github.com/user-attachments/assets/5dabbc9b-c649-4d1f-bc39-ba0006894d6b)
![image](https://github.com/user-attachments/assets/b5e8d250-02c1-4e8d-a9ee-e903cd1a775f)
![image](https://github.com/user-attachments/assets/1890c30f-8c7d-4df1-bea5-270480e81087)
![image](https://github.com/user-attachments/assets/ed28c5f3-b80c-4982-9912-1fb79f494fb7)
![image](https://github.com/user-attachments/assets/61d4b61a-5fdb-483d-b4de-aad91ada02c9)



---

$1
**Where is `story-index.txt` stored?** We’ll put it in our `story-blog` folder on the `main` branch, just like our other stories.

$2 (or `master`) branch:
   ```bash
   cd ~/story-blog
   git checkout main
   ```
2. Make sure your remote (like `origin`) is set to your GitHub repository.
3. Now create a file called `story-index.txt` (it can have a little typo to cause conflict later!).

---

## Main Lab

### 1. Max Commits a New `story-index.txt`

```bash
git add story-index.txt

git commit -m "Add index of stories"
```
This means Max wrote down all the story names in one file. Great!

### 2. Pushing Changes Gets Rejected

```bash
git push -u origin master
```

Git complains that the remote has changes that Max doesn’t have yet. We need to **pull**.

> **Kid-Friendly Explanation**: The online version has been updated by someone else. You can’t push your changes on top of it until you grab their new changes.

---

### 3. Pulling Causes a Conflict

```bash
git pull origin master
```

You might see something like:

```
Auto-merging story-index.txt
CONFLICT (content): Merge conflict in story-index.txt
```

**What’s happening?** Sarah changed `story-index.txt` on GitHub (the remote), and Max changed it too. Git sees two different versions of the **same line**.

> **Why a Conflict?** It’s like two classmates writing different words on the same line of a story. The teacher (Git) doesn’t know which line is correct.

### 4. Checking Logs and the Conflict

```bash
git log origin/master
# Shows that Sarah had the last commit.

cat story-index.txt
# Might show conflict markers.
```

Conflict markers look like this:
```
<<<<<<<< HEAD
1. The Lion and the Mooose
=======
1. The Lion and the Mouse
>>>>>>> origin/master
2. The Frogs and the Ox
3. The Fox and the Grapes
...
```

- `HEAD` is Max’s version.
- `origin/master` is Sarah’s version.

---

### 5. Fix the File, Then Commit
Max decides to fix the spelling and keep Sarah’s version:

```bash
cat << EOF > story-index.txt
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF

git add story-index.txt

git commit -m "Resolved merge conflict and merged story index"

git push -u origin master
```

All better now!

> **Kid-Friendly Explanation**: You erase the scribbles and write what you want the final line to say, then tell Git, “This is correct!”

---

## Summary
1. **Conflict**: When two people change the same line, Git doesn’t know which line to keep.
2. **Fix**: You open the file, remove the conflict markers (`<<<<<<` and `>>>>>>>`), and keep the good text.
3. **Commit**: You commit again to confirm that the file is now correct.

You’ve solved a merge conflict! Awesome job!

---

**Next**: [Lab 9: Git Forking](09_git_forking.md)



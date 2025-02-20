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

## The Setup (Ensuring a Conflict)

**Goal**: Make sure Sarah and Max both edit the same file so that Git can’t figure out whose change is correct.

1. **Max:** On your local computer (on the `main` branch in `story-blog`), create a new file with a small typo:
   ```bash
   cd ~/story-blog
   git checkout main

   cat << EOF > story-index.txt
   1. The Lion and the Mooose
   2. The Frogs and the Ox
   3. The Fox and the Grapes
   4. The Donkey and the Dog
   EOF

   git add story-index.txt
   git commit -m "Add index of stories (typo: Mooose)"
   ```
2. **Sarah:** Meanwhile, on GitHub’s **main** branch, open or create the **same** file `story-index.txt` but **without** the typo:
   ```
   1. The Lion and the Mouse
   2. The Frogs and the Ox
   3. The Fox and the Grapes
   4. The Donkey and the Dog
   ```
   Commit it directly on GitHub.

**Now** both Max and Sarah have changed the same line differently.

---

## Main Lab

### 1. Max Tries to Push

After Max commits locally, he does:
```bash
git push -u origin main
```
Git complains that there are changes on the remote (Sarah’s edit) that Max doesn’t have.

> **Kid-Friendly**: Someone changed the same line online, so you need to see those changes first.

### 2. Pulling Causes a Conflict
```bash
git pull origin main
```
Git sees **two** different lines for `story-index.txt`:
- **Max’s** line: `1. The Lion and the Mooose`
- **Sarah’s** line: `1. The Lion and the Mouse`

So it yells:
```
Auto-merging story-index.txt
CONFLICT (content): Merge conflict in story-index.txt
```

**Why a Conflict?** It’s like two friends both trying to correct the same sentence in a story differently.

### 3. Checking Logs and the Conflict

```bash
git log origin/main
# Shows that Sarah had the last commit online.

cat story-index.txt
# Might show conflict markers.
```

Conflict markers look like:
```
<<<<<<<< HEAD
1. The Lion and the Mooose
=======
1. The Lion and the Mouse
>>>>>>> origin/main
2. The Frogs and the Ox
3. The Fox and the Grapes
...
```

---

### 4. Fix the File, Then Commit
Max decides to **keep** Sarah’s spelling (`Mouse`) and remove the markers:

```bash
cat << EOF > story-index.txt
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF

git add story-index.txt

git commit -m "Resolved conflict: corrected spelling to 'Mouse'"

git push -u origin main
```

All better now!

> **Kid-Friendly Explanation**: You erase the scribbles, keep the line you want, and tell Git, “This is the final version.”

---

## Summary
1. **Conflict**: When two people change the same line, Git doesn’t know which line to keep.
2. **Fix**: You open the file, remove the conflict markers (`<<<<<<` and `>>>>>>>`), and keep the line you prefer.
3. **Commit**: You commit again to confirm that the file is now correct.

You’ve solved a merge conflict! Awesome job!

---

**Next**: [Lab 9: Git Forking](09_git_forking.md)

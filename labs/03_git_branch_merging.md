***"The people who are crazy enough to think they can change the world, are the ones who do." – Steve Jobs***
<br><br>


# Lab 3: Git Branch Merging
![image](https://github.com/user-attachments/assets/96f8b44f-7075-47b9-a7ac-386407474fd9) ![image](https://github.com/user-attachments/assets/073d11f1-f7d7-4c5b-87aa-acc8de59a32c) ![image](https://github.com/user-attachments/assets/eb99e756-4957-4df7-8118-b4c72041ceed) ![image](https://github.com/user-attachments/assets/b9e58837-9866-4150-8db0-aef1a08b64b9) ![image](https://github.com/user-attachments/assets/42a359c2-14a2-4895-80aa-7473f4366fd7) ![image](https://github.com/user-attachments/assets/ef80e53d-b661-4295-9518-7961cba71d47) 

### **Objectives**
By completing this lab, you will:  

1. **Switch Between Branches**  
   - Learn how to navigate between different branches using `git checkout`.  

2. **Identify Existing Branches**  
   - Use `git branch` to check the number of branches in a repository.  

3. **Review Commit History**  
   - Understand how to inspect the commit history of multiple branches using `git log`.  

4. **Merge a Feature Branch into Master**  
   - Perform a branch merge using `git merge` to integrate changes from a feature branch into the main branch.  

This lab will reinforce core Git skills essential for managing version control in collaborative workflows. 🚀


1. Switch back to master branch:
```
git checkout master
```

2. How many branches?  There are two:
```
git branch
# Output:
# * master
#   story/frogs-and-ox
```

3. Let's check git log:
```
# The new story Sarah wrote is in the story/frogs-and-ox branch. It's time to merge the branch and bring it to the master branch.
# But before that look at the log of the master and story/frogs-and-ox branches and identify how many commits there have been in the past on each branch.

git log master
git log story/frogs-and-ox
```

4. Time to merge the `story/frogs-and-ox` branch with `master`:
```
git merge story/frogs-and-ox -m "Merge branch 'story/frogs-and-ox'"
```




## Summary
In this lab, you practiced switching between branches, reviewing commit history, and merging branches in Git.

#### 1. **Switching to the Master Branch**  
   - You started by switching back to the `master` branch using:
     ```bash
     git checkout master
     ```

#### 2. **Checking Available Branches**  
   - You verified that there were two branches:  
     - `master` (the main branch)  
     - `story/frogs-and-ox` (a feature/story branch)

   - To list branches, you used:
     ```bash
     git branch
     ```

#### 3. **Reviewing Commit History**  
   - Before merging, you inspected the commit history of both branches using:
     ```bash
     git log master
     git log story/frogs-and-ox
     ```
   - This helped in identifying the number of commits made on each branch.

#### 4. **Merging the Branch**  
   - Finally, you merged the `story/frogs-and-ox` branch into `master` using:  
     ```bash
     git checkout master
     git merge story/frogs-and-ox -m "Merge branch 'story/frogs-and-ox'"
     ```
   - This incorporated all the changes from the feature branch into the main branch.

By completing this lab, you have learned how to navigate branches, check commit history, and perform a branch merge—essential skills for collaborative Git workflows.




<br><br>

**Next:** [Lab 4: Merging Branches](04_git_remote_and_git_push.md)
















# Lab 3: Git Branch Merging (5th Grader Edition)

![image](https://github.com/user-attachments/assets/96f8b44f-7075-47b9-a7ac-386407474fd9)
![image](https://github.com/user-attachments/assets/073d11f1-f7d7-4c5b-87aa-acc8de59a32c)
![image](https://github.com/user-attachments/assets/eb99e756-4957-4df7-8118-b4c72041ceed)
![image](https://github.com/user-attachments/assets/b9e58837-9866-4150-8db0-aef1a08b64b9)
![image](https://github.com/user-attachments/assets/42a359c2-14a2-4895-80aa-7473f4366fd7)
![image](https://github.com/user-attachments/assets/ef80e53d-b661-4295-9518-7961cba71d47)

## Quick Review
- In **Lab 2**, we made two stories:
  - **“Lion and the Mouse”** (on the `master` branch)
  - **“Frogs and the Ox”** (on `story/frogs-and-ox`)

- We also **fixed a typo** on `master`, then **finished** the new story on `story/frogs-and-ox`.

Now it’s time to **combine** (merge) these changes so everything is on the main branch.

---

## Why Merge?
**Merging** is like **adding your side story** back into the **main story** so everyone can read it. If you keep your “Frogs and the Ox” story on a separate branch, nobody on the main branch knows about it. Once you merge, it’s all in one place!

---

## Objectives
1. **Switch** branches using `git checkout`.
2. **See** your branches with `git branch`.
3. **Check** your branch “history” with `git log`.
4. **Merge** the story branch (`story/frogs-and-ox`) into the main branch (`master`).

---

## Step-by-Step Instructions

### 1. Go Back to the Main Road
```bash
git checkout master
```
This command moves you to the **master** branch. Picture leaving a side path and returning to the main road.

### 2. See Which Roads (Branches) Exist
```bash
git branch
# Output:
# * master
#   story/frogs-and-ox
```
Here you see two branches:
- `master` (that’s you, the star `*` means you’re standing here)
- `story/frogs-and-ox`

### 3. Look at the Past Commits (History)
```bash
# The "Frogs and the Ox" story is on story/frogs-and-ox.
# We want to add that story to the master branch.
# But first, let's see what happened on each branch so far:

git log master
git log story/frogs-and-ox
```
This is like reading each branch’s diary.

### 4. Merge the Frog Story into Master
```bash
git merge story/frogs-and-ox -m "Merge branch 'story/frogs-and-ox'"
```
You’ve now **combined** the frog story into the `master` branch. Yay!

---

## Summary
1. You **returned** to `master` (`git checkout master`)—think of that as the main road.
2. You **listed** your branches (`git branch`) and found `master` plus `story/frogs-and-ox`.
3. You **checked** both branch histories (`git log`)—like reading diaries for each one.
4. You **merged** the frog story branch into `master` (`git merge story/frogs-and-ox`).

Now you have **both** “Lion and the Mouse” **and** “Frogs and the Ox” on the same branch—`master`—where everyone can see them.

---

## Next Steps
Now that you’ve learned **merging**, you can explore **what happens if there’s a conflict** (like two people changing the same line). You’ll need to decide which version to keep—or mix them together. Great job merging branches!

**Continue to:** [Lab 4: Merging Branches (Advanced)](04_git_remote_and_git_push.md)





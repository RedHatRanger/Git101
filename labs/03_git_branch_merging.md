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

## Introduction
In **Lab 2**, you learned how to create new branches for different stories in your project:
- **Lion and the Mouse** (on the main/master branch)
- **Frogs and the Ox** (on a branch called `story/frogs-and-ox`)

You also learned how to fix a typo on the main branch and then finish writing your story on the feature branch. **Now** it’s time to bring those changes together so everyone can see the new story on the main branch. In Git, that’s called a **merge**.

---

## Objectives
By the end of this lab, you will:
1. **Switch between branches** using `git checkout`.
2. **See what branches exist** using `git branch`.
3. **Check commit histories** with `git log`.
4. **Merge** the `story/frogs-and-ox` branch into `master`.

---

## Why Merge?
Merging means you’re **combining** your work from one branch into another—like adding a new chapter to the same book. If you made a new story on `story/frogs-and-ox`, merging puts it back on the main branch, so everyone has the **latest** and **greatest** version.

---

## Step-by-Step Instructions (Verbatim Code Snippets)
Below are the **exact** commands from this lab, with some kid-friendly explanations:

1. **Switch back to the master branch**:
   ```bash
git checkout master
```
   Think of it like going back to the main road.

2. **How many branches do we have?**
   ```bash
git branch
# Output:
# * master
#   story/frogs-and-ox
```
   This shows two branches: `master` and `story/frogs-and-ox`.

3. **Check the commit logs**:
   ```bash
# The new story Sarah wrote is in the story/frogs-and-ox branch.
# It's time to merge the branch into master.
# But first, look at the log of each branch to see how many commits each has.

git log master
git log story/frogs-and-ox
```
   This is like looking at each branch’s journal entries.

4. **Time to merge** the `story/frogs-and-ox` branch into `master`:
   ```bash
git merge story/frogs-and-ox -m "Merge branch 'story/frogs-and-ox'"
```
   You’ve now combined the “Frogs and the Ox” story into the main branch!

---

## Summary

1. **Switch to Master**: You hopped back onto the main road with `git checkout master`.
2. **List Branches**: You saw there were two branches—`master` and `story/frogs-and-ox`.
3. **Review Commit History**: You looked at each branch’s “timeline” with `git log`.
4. **Merge**: You used `git merge` to bring `story/frogs-and-ox` into `master`, so now both stories are on the main branch.

Merging is a crucial skill in Git because it allows many people (or just you!) to work on different parts of a project at the same time, then combine everything into one final place.

---

## Next Steps
After you’ve merged your changes, you’re ready to explore more advanced Git features—like dealing with conflicts if you and someone else changed the **same** file. But for now, great job on learning to merge branches!

**Continue to:** [Lab 4: Merging Branches (Advanced)](04_git_remote_and_git_push.md)



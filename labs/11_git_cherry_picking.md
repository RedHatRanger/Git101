

>We now have a copy of that `Changed first story` commit on the `master` branch!

<br><br>
# Main Lab

```
git log master --oneline
# f2ba941 Updated the story index file
```

2. Now, let's cherry pick that one:
```
git cherry-pick f2ba941
```


















***"To master a new technology, you will have to play with it." – Jordan Peterson***
<br><br>

# Lab 11: Git Cherry-Picking (5th Grader Edition)

![image](https://github.com/user-attachments/assets/c8a2eb1b-b440-493a-9d7b-520e53ae5a1e)
![image](https://github.com/user-attachments/assets/3d7912b5-ffb4-48e4-aa68-576d4cb1e0e8)

![image](https://github.com/user-attachments/assets/c8a2eb1b-b440-493a-9d7b-520e53ae5a1e)
![image](https://github.com/user-attachments/assets/3d7912b5-ffb4-48e4-aa68-576d4cb1e0e8)
![image](https://github.com/user-attachments/assets/527a9d0f-2b5d-4d78-ab31-9133ecaf93db)
![image](https://github.com/user-attachments/assets/8ca93169-7339-4284-801c-f8f855bc90b9)
![image](https://github.com/user-attachments/assets/1b32028b-5cb3-48c3-8f1f-c1145ed33c14)
![image](https://github.com/user-attachments/assets/55b9506f-64a8-4dd7-8607-efe285980ee4)
![image](https://github.com/user-attachments/assets/251b2f76-efb7-4705-807c-4470b33d333f)

## Quick Review of Previous Labs
- **Lab 1**: We set up Git and saved our first files.
- **Lab 2**: We created branches so we could try new things safely.
- **Lab 3**: We merged those branches back into the main code.
- **Lab 4**: We pushed our project to a remote and learned to pull.
- **Lab 5**: We cloned a remote repo to work on locally.
- **Lab 6**: We opened Pull Requests so others could check our changes.
- **Lab 7**: We fetched and pulled updates to stay in sync.
- **Lab 8**: We dealt with merge conflicts when two people changed the same line.
- **Lab 9**: We forked a project to make our own copy.
- **Lab 10**: We used interactive rebasing to rearrange or squash commits.

**Now**, in **Lab 11**, we’ll talk about **cherry-picking**—a way to grab just **one** specific commit from another branch and copy it into your current branch.

---

## Why Cherry-Pick?
Sometimes you only want **one** commit’s changes, not the entire branch. **Cherry-picking** is like seeing a single page in a friend’s notebook that you really like and **copying** just that page into your notebook, without copying everything else.

---

## The Setup
Let’s say we have two branches: `master` and `feature`. On `feature`, there’s a commit that changes the “first story.” We don’t want all of feature’s changes, but we **do** want that single commit.

> **Kid-Friendly**: It’s like your friend wrote a big chapter, but you only like one paragraph and want it in your chapter.

---

## Main Lab

### 1. Identify the Commit You Want
```bash
git log master --oneline
```
From the output, we see a commit `f2ba941` titled “Updated the story index file” that we want on `master`.

### 2. Cherry-Pick That Commit
```bash
git cherry-pick f2ba941
```
Git **copies** that one commit (the changes and message) onto your current branch—**master** in this example.

> **Now** the “first story” changes are on `master`, even though the rest of `feature` is not.

### 3. Verify It Worked
Check `git log --oneline` on `master` or open your changed file. You should see that single commit’s changes applied.

> **Kid-Friendly**: You took just that special paragraph from your friend’s branch and pasted it into your branch.

---

## Understanding the Images
1. **Cherry-Pick Explanation**: The first images show the concept of copying a single commit from one branch to another.
2. **Selecting the Commit**: You see an example `git log master --oneline`, then we pick the hash `f2ba941`.
3. **Cherry-Pick Action**: We run `git cherry-pick f2ba941`, and Git copies that commit’s changes.
4. **Result**: The `master` branch now has that single commit (“Changed first story” or “Updated story index file”).

In short, the pictures show you picking out exactly one commit from a list and bringing it over.

---

## Summary
1. **Cherry-Pick**: Copy exactly one commit from another branch into your current branch.
2. **Use Cases**: If you only need one fix or one small feature, not everything else.
3. **How**: Use `git log` to find the commit hash, then `git cherry-pick <commit-id-hash>`.

Cherry-picking is super helpful if you made a fix on the wrong branch or only want a specific fix from a friend’s branch. Good job learning to pick just the best pieces!

---

**Next**: [Lab 12: Git Reset and Git Revert](12_git_reset_and_git_revert.md)

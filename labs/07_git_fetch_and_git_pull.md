***"In learning you will teach, and in teaching you will learn." – Phil Collins***
<br><br>

# Lab 7: Git Fetching and Pulling (5th Grader Edition)

![image](https://github.com/user-attachments/assets/8afb50ac-1e45-496b-9c15-8b4ab8de80d8)
![image](https://github.com/user-attachments/assets/c2727881-ffb1-4e9f-9391-2c02abf47e94)
![image](https://github.com/user-attachments/assets/f4e56dd4-efa2-4d3c-8d54-08f8937c574e)

## Quick Review
- **Lab 1**: We learned to set up Git and make our first commits.
- **Lab 2**: We created branches to safely work on new stories or features.
- **Lab 3**: We merged our new branches back into the main branch.
- **Lab 4**: We learned about remotes (like GitHub) and how to push/pull.
- **Lab 5**: We cloned an existing remote repo to our own computer.
- **Lab 6**: We used Pull Requests to show our changes and get them approved.

Now, in **Lab 7**, we’ll explore **fetch** and **pull**. These commands help us **get** changes from a remote repo so our local code is always up to date.

---

## What is a Pull?
Imagine your friend updated the story in a shared notebook. Now you want that new chapter in **your** notebook. **Pull** is the command that:

1. **Finds** (fetches) your friend’s new chapter.
2. **Adds** it (merges) into your notebook automatically.

So you don’t have to do two separate steps.

---

<br><br>
## Lab Setup: Creating the "Donkey and the Little Dog" Story on the Remote
1. **Go to GitHub** (or any Git remote hosting you’re using) in your **main** branch.
2. **Create a new file** called `donkey-and-dog.txt` (or “The Donkey and the Little Dog”).
3. **Paste** the entire donkey story below into that file and commit it directly on GitHub’s main branch:

```
--------------------------------------------
      THE DONKEY AND THE LITTLE DOG
--------------------------------------------

A man had a little dog, and he was very fond of it. He would pat its head, and take it on his knee, and talk to it. Then he would give it little bits of food from his own plate.

A donkey looked in at the window and saw the man and the dog.

"Why does he not make a pet of me?" said the donkey.

"It is not fair. I work hard, and the dog only wags its tail, and barks, and jumps on its master's knee. It is not fair."

Then the donkey said to himself, "If I do what the dog does, he may make a pet of me."

So the donkey ran into the room. It brayed as loudly as it could. It wagged its tail so hard that it knocked over a jar on the table. Then it tried to jump on to its master's knee.

The master thought the donkey was mad, and he shouted, "Help! Help!" Men came running in with sticks, and they beat the donkey till it ran out of the house, and they drove it back to the field.

"I only did what the dog does," said the donkey," and yet they make a pet of the dog, and they beat me with sticks. It is not fair."
```

**Important**: Your **local** copy doesn’t know about this file yet.

---

## Main Lab

### 1. Let's Play with `fetch`
This **downloads** new changes from the remote **without** automatically merging them.
```bash
git checkout main
# Make sure we're on the main branch

git fetch origin main
# Pull down new commits, but don't merge yet
```
Now Git has quietly grabbed the donkey story from GitHub, but it hasn’t added it to your files yet.

### 2. See All the Branches
```bash
git branch -a
```
This shows local branches **and** remote branches.

### 3. Merge the Remote Changes
```bash
git merge origin/main
```
We combine the **fetched** donkey story from `origin/main` into our local `main`. Now you should see the donkey story file in your local folder.

### 4. `git pull` = `git fetch + git merge`
```bash
git pull origin main
```
This command **fetches** new stuff from the remote and **merges** it in, all in one step. So in the future, you can skip the two-step process.

---

### Why the Donkey Story Appeared
Because someone added the donkey story on GitHub (the remote), you didn’t have it locally. **Fetching** got the new data, and **merging** updated your files.

---

## Summary
- **`git fetch`**: Grabs changes from the remote but does **not** merge them.
- **`git merge origin/main`**: Merges the fetched changes into our local `main`.
- **`git pull`**: Does both fetch and merge in one go.

With fetch and pull, you can always keep your local code in sync with what’s happening online (like new stories!). Great job staying up to date!

---

**Next**: [Lab 8: Git Merge Conflicts](08_git_merge_conflicts.md)

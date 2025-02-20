># The Setup
>- Be sure you still have the repo you cloned earlier from Lab 5.

# Main Lab
1. Let's create a new branch that max can work on safely without touching the main branch:
```
git checkout -b story/fox-and-grapes
```

<br><br>
2. Make a slight change to the `fox-and-grapes.txt`, stage, then commit to the new branch:
```
git add fox-and-grapes.txt 
git commit -m "Updated fox-and-grapes story"
```

<br><br>
3. Push the committed changes to the new remote branch:
```
git push -u origin story/fox-and-grapes

# You will have to enter the password if you didn't add SSH keys in GitHub
```

<br><br>
4. Access GitHub, GitBucket, or Gitea's UI portal to submit a Pull Request (PR) to merge the changes to master:
```
PR title : Added fox-and-grapes story

PR pull from branch: story/fox-and-grapes (source)

PR merge into branch: master (destination)

Add tom as reviewer through the Git Portal UI
```

> It should look something like this when you are finished:



**Next:** [Lab 7: Git Fetch & Git Pull](07_git_fetch_and_git_pull.md)


***"One big reason for a winning attitude is that you will take the necessary steps and not quit when the going gets difficult." – Don M.Green***
<br><br>

# Lab 6: Pull Requests (5th Grader Edition)

![image](https://github.com/user-attachments/assets/6927865a-e6de-4d81-88f2-7d7fc81817e0)
![image](https://github.com/user-attachments/assets/912bc1a0-320f-480b-8ca0-8f1664699f42)
![image](https://github.com/user-attachments/assets/fa8985fd-ce42-4066-8dcd-68a74db3fc66)
![image](https://github.com/user-attachments/assets/c54de7c4-652e-4886-a6af-c9c52b50752d)
![image](https://github.com/user-attachments/assets/c5e9138a-4509-4d10-9c52-5863630f3b8a)
![image](https://github.com/user-attachments/assets/6c129e1a-2cb7-491f-9f94-ab8222e5c16a)
![image](https://github.com/user-attachments/assets/02ed2d63-d07c-48d7-ad9e-01306b74d4fe)
![image](https://github.com/user-attachments/assets/e9030a38-8d37-4cda-8ad3-e2a9ee01bf9d)
![image](https://github.com/user-attachments/assets/1aee80a7-59f5-42dc-b04e-d550ba835c5b)

## Quick Review
- **Lab 1**: We set up Git and learned how to make commits.
- **Lab 2**: We branched our code to try out different “story” ideas.
- **Lab 3**: We merged those branches back into the main road.
- **Lab 4**: We put our project online with a remote like GitHub.
- **Lab 5**: We learned to clone a project from GitHub to our computer.

Now it’s time to talk about **Pull Requests**, which let you share your changes so someone else can check them before they get added to the main branch.

---

## What is a Pull Request (PR)?
A **Pull Request** is like saying, “Hey, I have these new changes. Could you please review them and then add them to the main story?” It’s a polite way to show your work, get feedback, and eventually merge it.

---

## The Setup
Make sure you have the repo you **cloned** earlier from Lab 5. We’ll make a new branch, change a file, and then ask (via Pull Request) to add those changes to `master`.

---

## Main Lab

### 1. Create a New Branch for Your Changes
```bash
git checkout -b story/fox-and-grapes
```
Here, we’re making a safe side path (branch) for our “fox-and-grapes” story, so we don’t break anything on `master`.

---

### 2. Update `fox-and-grapes.txt`, Stage, and Commit
```bash
git add fox-and-grapes.txt

git commit -m "Updated fox-and-grapes story"
```
You’ve just saved your changes on this new branch.

---

### 3. Push to Your Remote Branch
```bash
git push -u origin story/fox-and-grapes
```
Now your new branch is online. If you didn’t add SSH keys, you may have to type your password.

---

### 4. Submit a Pull Request (PR)
Go to GitHub (or Gitea, etc.) and open a Pull Request:
- **Title**: “Added fox-and-grapes story”
- **From Branch**: `story/fox-and-grapes` (source)
- **Into Branch**: `master` (destination)
- **Request a Reviewer** (like “tom”)

A PR says, “Please check my code. If it looks good, let’s merge it!”

- It should look like this when you are finished:
![image](https://github.com/user-attachments/assets/27f4225f-e16d-44b2-8e84-033098201294)

---

### 5. Reviewer Approves (or Rejects)
```bash
As Tom:
1. Go to the story-blog repo
2. Click on Pull Requests
3. Open "Added fox-and-grapes story"
4. Click on "Files changed" to see changes
5. Click "Review" -> "Approve" (or comment)
```
If Tom likes your changes, he can approve.

---

### 6. Merge into Master
```bash
As Sarah:
1. Go back to the Pull Request
2. Click Merge Pull Request
3. Confirm
4. The PR should say "Merged" when done
```
Congratulations! Your changes are now **officially** part of the master branch.

---

## Summary
1. You made a branch to safely edit `fox-and-grapes.txt`.
2. You pushed that branch online.
3. You opened a **Pull Request** so someone else could review your changes.
4. They **approved** (or commented), and then you **merged** into `master`.

Pull Requests are super handy if you have a team—or if you just want to make sure your changes are good before adding them to the main story!

---

**Next**: [Lab 7: Git Fetch & Git Pull](07_git_fetch_and_git_pull.md)

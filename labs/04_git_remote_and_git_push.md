***"Without Git, software development would just be a bunch of people overwriting each other’s files." – Linus Torvalds***
<br><br>


# Lab 4: Working with Remotes
![image](https://github.com/user-attachments/assets/f9400c6a-b5cd-4207-9cb2-0b6a00ab6fd0) ![image](https://github.com/user-attachments/assets/0dc19ba3-d044-4081-abb7-0e33af541627) ![image](https://github.com/user-attachments/assets/3aefaf69-ed0e-4994-b83b-834cbae0275e) ![image](https://github.com/user-attachments/assets/ac18bc45-77f6-4083-b72c-e2b35567196a) ![image](https://github.com/user-attachments/assets/8e509219-b045-429d-bda1-3fc29ca76d1b) ![image](https://github.com/user-attachments/assets/e776eb96-121e-4059-9f73-352294418164) ![image](https://github.com/user-attachments/assets/499fffd7-7553-489e-bcb5-38af95f89539) 



In **Lab 4**, you'll learn how to connect local repositories to remote servers (like GitHub, GitLab, or Bitbucket), push and pull changes, and collaborate more effectively.

---

## Objectives

  I. Add a remote to your local repository \
 II. Push local changes to a remote repository \
III. Pull changes from the remote to your local machine \
 IV. Understand basic remote-tracking branches 

<br><br><br><br>

## I. Adding a Remote Repo
- Create a repository on GitHub (or similar), called `story-blog`.
- Click `Code` and copy the URL `http://.../.../story-blog.git`.
- In your local repo:
  ```bash
  git remote add origin https://github.com/<your-username>/story-blog.git
  ```

Verify:
```bash
git remote -v
```

<br><br>
## II. Pushing Changes
1. Push your local `master` branch to the remote:
```bash
git push -u origin master

# Enter the Username and Password if prompted
# Tip: to avoid having to type in the credentials each time, consider adding your local machine's SSH keys to GitHub or Gitea
```

2. After the first push, you can simply use:
```bash
git push
```

3. Verify on GitHub (or your remote) that your files have appeared.
![image](https://github.com/user-attachments/assets/f7a15c68-3a77-4a0c-b846-73c87a741518)


<br><br>
## III. Pulling Changes

If changes were made remotely by you or teammates:
```bash
git pull
```
>This fetches and merges remote commits into your local branch.

<br><br>
## IV. Working with Remote-Tracking Branches

When you create a new local branch and want to track it remotely:
```bash
git checkout -b feature/new-ui
git push -u origin feature/new-ui
```
>Now your local `feature/new-ui` branch is linked to `origin/feature/new-ui`.

<br><br>
## Summary
You can now collaborate via GitHub (or other hosting platforms), ensuring all team members stay in sync. Remote repositories form the backbone of distributed version control.

<br><br>
**Next:** [Lab 5: Undoing Changes](05_undoing_changes.md)










# Lab 4: Working with Remotes (Simplified for 5th Graders)

> ***"Without Git, software development would just be a bunch of people overwriting each other’s files."*** — Linus Torvalds

![image](https://github.com/user-attachments/assets/f9400c6a-b5cd-4207-9cb2-0b6a00ab6fd0)
![image](https://github.com/user-attachments/assets/0dc19ba3-d044-4081-abb7-0e33af541627)
![image](https://github.com/user-attachments/assets/3aefaf69-ed0e-4994-b83b-834cbae0275e)
![image](https://github.com/user-attachments/assets/ac18bc45-77f6-4083-b72c-e2b35567196a)
![image](https://github.com/user-attachments/assets/8e509219-b045-429d-bda1-3fc29ca76d1b)
![image](https://github.com/user-attachments/assets/e776eb96-121e-4059-9f73-352294418164)
![image](https://github.com/user-attachments/assets/499fffd7-7553-489e-bcb5-38af95f89539)

## Quick Review
- **Lab 2**: We learned about **branches**—little paths off of the main path.
- **Lab 3**: We learned about **merging** those branches back together.

Now, in **Lab 4**, we want to **share** our project with friends or classmates. We do this by pushing our files to an **online place** called a **remote** (like GitHub). Think of it as putting your project in a **safe online box** where everyone can grab it!

---

## What is a Remote?
A **remote** is an online copy of your Git project. You can **push** (send) your changes to the remote so others can see them. You can also **pull** (download) changes if someone else made updates in the remote.

---

## Objectives
1. **Add a remote** to connect your local (computer) project to an online place.
2. **Push** your local changes so they appear in the remote.
3. **Pull** changes from the remote if others have updated the code.
4. Learn how to make **new branches** that also live on the remote.

---

## I. Adding a Remote
1. **Make a new repository on GitHub** (or another website). Call it **`story-blog`**.
2. Copy the link (URL) of that repo (like `https://github.com/your-name/story-blog.git`).
3. In your local project folder:

```bash
git remote add origin https://github.com/your-name/story-blog.git
```

4. Check it worked:
```bash
git remote -v
```
This shows **where** your remote is.

---

## II. Pushing Changes

### First Push
```bash
git push -u origin master
```
- **`-u origin master`** means “Set the main branch (`master`) to upload to `origin` (the remote).”
- Enter your username/password if asked.

### After That
```bash
git push
```
This is all you need, because Git remembers where to send your changes.

### Check Online
Go to GitHub and look at your `story-blog` repo. You should see your files—like `lion-and-mouse.txt` and `frogs-and-ox.txt`—from the earlier labs.

---

## III. Pulling Changes
If your friend or teammate **fixes** something on GitHub, you want those fixes on your computer too. So you do:

```bash
git pull
```

This gets the newest stuff from the remote and **merges** it into your local code.

---

## IV. Remote-Tracking Branches
If you make a **brand new branch** on your computer, you might want it to show up online, too.

```bash
git checkout -b feature/new-ui
# Make a new branch

git push -u origin feature/new-ui
# Connect it to the remote
```

Now your local `feature/new-ui` branch is linked with `origin/feature/new-ui`. When you **push** or **pull**, Git knows they go together.

---

## Summary
- **Add a remote** so Git knows where your code lives online.
- **Push** to share your updates.
- **Pull** to get updates from others.
- **Remote-tracking branches** let new branches live online, too.

With **remotes**, everyone can work on the same code from different computers, all at once. No more emailing files back and forth!

---

## Next
Ready to fix mistakes or step back in time with Git? Check out [Lab 5: Undoing Changes](05_undoing_changes.md).


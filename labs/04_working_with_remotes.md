***"Without Git, software development would just be a bunch of people overwriting each other’s files." – Linus Torvalds***
<br><br>


# Lab 4: Working with Remotes
![image](https://github.com/user-attachments/assets/f9400c6a-b5cd-4207-9cb2-0b6a00ab6fd0) ![image](https://github.com/user-attachments/assets/0dc19ba3-d044-4081-abb7-0e33af541627) ![image](https://github.com/user-attachments/assets/3aefaf69-ed0e-4994-b83b-834cbae0275e) 









In **Lab 4**, you'll learn how to connect local repositories to remote servers (like GitHub, GitLab, or Bitbucket), push and pull changes, and collaborate more effectively.

---

## Objectives

  I. Add a remote to your local repository \
 II. Push local changes to a remote repository \
III. Pull changes from the remote to your local machine \
 IV. Understand basic remote-tracking branches 

<br><br><br><br>

## I. Adding a Remote Repo
- If you created a repository on GitHub (or similar), copy its URL.
- In your local repo:
  ```bash
  git remote add origin https://github.com/<your-username>/<repo-name>.git
  ```

Verify:
```bash
git remote -v
```

<br><br>
## II. Pushing Changes
1. Push your local `main` branch to the remote:
```bash
git push -u origin main
```

2. After the first push, you can simply use:
```bash
git push
```

3. Verify on GitHub (or your remote) that your files have appeared.


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


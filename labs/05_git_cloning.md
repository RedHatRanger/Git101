
# Main Lab:
1. Clone a Remote Repository (Use the SSH option):
```
git clone git@github.com:RedHatRanger/story-blog.git

# Output:
# Cloning into 'story-blog'...
# remote: Enumerating objects: 11, done.
# remote: Counting objects: 100% (11/11), done.
# remote: Compressing objects: 100% (10/10), done.
# remote: Total 11 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
# Receiving objects: 100% (11/11), 4.82 KiB | 987.00 KiB/s, done.
# Resolving deltas: 100% (2/2), done.


cd story-blog
```

<br><br>
2. Create YOUR Repository on GitHub, GitBucket, or Gitea [(Tutorial on YouTube)](https://www.youtube.com/watch?v=Oaj3RBIoGFc&t=653s).

<br><br>
3. Generate SSH keys from your local computer to distribute to GitHub:
```
ssh-keygen -t rsa -b 4096
```

<br><br>
4. Copy the `id_rsa.pub` contents and add it to GitHub [(Tutorial on YouTube)](https://www.youtube.com/watch?v=X40b9x9BFGo): \
![image](https://github.com/user-attachments/assets/9bb8a404-76bb-4c53-a542-f08096040ac0)
![image](https://github.com/user-attachments/assets/efd75bd0-80bb-47e7-a358-3bae961da3c1)

<br><br>
5. Stage some new changes...You may get an error for adding an anonymous commit:
- Add "The End" to the end of the `fox-and-grapes.txt` file and save it.
```
git add fox-and-grapes.txt
git commit -m "Added 'The End' to fox and grapes story"
```
![image](https://github.com/user-attachments/assets/31ed5081-cec1-4a31-be17-7600b6cd7138)

<br><br>
6. Configure your global git credentials:
```
git config --global user.name "John Smith"
git config --global user.email "jsmith@example.com"

# Then run the commands again to stage and commit:
git add fox-and-grapes.txt
git commit -m "Added 'The End' to fox and grapes story"

# Check the log for the user name and email information that you set up:
git log
```
![image](https://github.com/user-attachments/assets/14f004f8-2dbb-4e38-bf34-3022ece1230f)

<br><br>
6. Add the remote repository you setup 
```
git remote add origin git@github.com:RedHatRanger/story-blog.git
git push -u origin main

# (OPTIONAL) If `origin` exists, either choose another name, or remove the remote:
# (1) git remote add new-origin git@github.com:RedHatRanger/story-blog.git 
# (2) git remote remove origin

# (OPTIONAL) If you want to know what origin is:
# (1) git remote get-url --all origin

# Then repeat step 6
```










***"Question everything. Learn something. Answer nothing." – Euripides***
<br><br>

# Lab 5: Cloning Remote Repositories (5th Grader Edition)

![image](https://github.com/user-attachments/assets/bb0c006d-bdce-4b74-8e9e-222b9a8ce728)
![image](https://github.com/user-attachments/assets/cde069e9-5532-4201-8943-c076c4a166ef)
![image](https://github.com/user-attachments/assets/b4a24a1d-9072-466c-b16f-0fcba96f63a1)
![image](https://github.com/user-attachments/assets/6d9f09e2-e167-4eef-92be-f814c16e2ce6)
![image](https://github.com/user-attachments/assets/5797dff3-cf11-4760-a912-390f574cb392)

## Quick Review
- **Lab 1**: We got Git set up and learned the basics of saving changes (commits).
- **Lab 2**: We created new branches (like separate pathways for new stories).
- **Lab 3**: We merged our branch changes back into the main path.
- **Lab 4**: We pushed our project online to a remote, so friends could see and pull it.

Now, in **Lab 5**, we’ll learn how to **copy** (clone) an existing remote project from somewhere like GitHub down to our own computer.

---

## Setup Step: Resetting Your Git Info

If you need to remove old name/email settings:
```bash
git config --global --unset user.name
git config --global --unset user.email
```
It’s like erasing your old name tag so you can write a new one.

---

# Main Lab

## 1. Cloning a Remote Repository (Using SSH)

If your friend already put **story-blog** on GitHub and you want your own copy:
```bash
git clone git@github.com:RedHatRanger/story-blog.git

# Output:
# Cloning into 'story-blog'...
# remote: Enumerating objects: 11, done.
# ...

cd story-blog
```
You just **downloaded** all the project files (and history) into a new folder called `story-blog`.

---

## 2. Make Your Own Repository

You could also create **your own** remote place on GitHub or Gitea, for example:
1. Go to GitHub.
2. Click **New Repository**, name it `story-blog`.
3. Copy the SSH link.

For a more detailed explanation, watch this [YouTube tutorial](https://www.youtube.com/watch?v=Oaj3RBIoGFc&t=653s).

---

## 3. Generate SSH Keys

SSH keys let you push and pull from GitHub **without** typing a password each time.

```bash
ssh-keygen -t rsa -b 4096
```

This makes two files:
- **id_rsa** (private, don’t share!)
- **id_rsa.pub** (public, paste this into GitHub)

See [this video](https://www.youtube.com/watch?v=X40b9x9BFGo) if you’re stuck.

---

## 4. Copy `id_rsa.pub` to GitHub

Open `id_rsa.pub` and copy everything inside. Go to GitHub **Settings** > **SSH Keys**, and paste it.

Now GitHub trusts your computer when you push or pull.

---

## 5. Stage Some Changes

In your new `story-blog` folder, add **"The End"** to `fox-and-grapes.txt` (or whichever file you have):
```bash
git add fox-and-grapes.txt
git commit -m "Added 'The End' to fox and grapes story"
```

If Git complains about no name or email, do step 6.

---

## 6. Set Your Global Git Credentials

```bash
git config --global user.name "John Smith"
git config --global user.email "jsmith@example.com"
```

Then try again:
```bash
git add fox-and-grapes.txt
git commit -m "Added 'The End' to fox and grapes story"

git log
# Should show your commit with your new name and email.
```

---

## 7. Add Your Own Remote and Push

If you want this local code to point to **your** GitHub:
```bash
git remote add origin git@github.com:RedHatRanger/story-blog.git

git push -u origin main
```

### Optional Tips
- If `origin` is already taken, pick another name, or remove it:
```bash
git remote remove origin
```
- Check what `origin` is:
```bash
git remote get-url --all origin
```

---

## Summary
1. **Clone** a repo if you want your own copy of someone else’s project.
2. **(Optional)** Make your own remote online.
3. **Create SSH keys** so you can push/pull more easily.
4. **Add changes**, then **push** them so everyone can see.

**Great job!** You can grab code from the internet or share your own code so others can join.

---

**Next**: [Lab 6: Pull Requests](06_git_pull_requests.md)

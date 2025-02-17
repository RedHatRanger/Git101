***"Learning never exhausts the mind." — Leonardo da Vinci***
<br><br>

# Lab 5: Cloning Remote Repositories
![image](https://github.com/user-attachments/assets/bb0c006d-bdce-4b74-8e9e-222b9a8ce728) ![image](https://github.com/user-attachments/assets/cde069e9-5532-4201-8943-c076c4a166ef) ![image](https://github.com/user-attachments/assets/b4a24a1d-9072-466c-b16f-0fcba96f63a1) ![image](https://github.com/user-attachments/assets/6d9f09e2-e167-4eef-92be-f814c16e2ce6) ![image](https://github.com/user-attachments/assets/56b26d71-c6e9-4f4d-9a77-8532e8ba5bbb) 

# The Setup:
```
git config --global --unset user.name
git config --global --unset user.email
```

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

2. Create YOUR Repository on GitHub, GitBucket, or Gitea [(Tutorial on YouTube)](https://www.youtube.com/watch?v=Oaj3RBIoGFc&t=653s).

3. Generate SSH keys from your local computer to distribute to GitHub:
```
ssh-keygen -t rsa -b 4096
```

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


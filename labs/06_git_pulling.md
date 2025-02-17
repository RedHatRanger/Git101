***"One big reason for a winning attitude is that you will take the necessary steps and not quit when the going gets difficult." – Don M.Green***
<br><br>

# Lab 6: Pull Requests
![image](https://github.com/user-attachments/assets/6927865a-e6de-4d81-88f2-7d7fc81817e0) ![image](https://github.com/user-attachments/assets/912bc1a0-320f-480b-8ca0-8f1664699f42) ![image](https://github.com/user-attachments/assets/fa8985fd-ce42-4066-8dcd-68a74db3fc66) ![image](https://github.com/user-attachments/assets/c54de7c4-652e-4886-a6af-c9c52b50752d) ![image](https://github.com/user-attachments/assets/c5e9138a-4509-4d10-9c52-5863630f3b8a) ![image](https://github.com/user-attachments/assets/6c129e1a-2cb7-491f-9f94-ab8222e5c16a) ![image](https://github.com/user-attachments/assets/02ed2d63-d07c-48d7-ad9e-01306b74d4fe) ![image](https://github.com/user-attachments/assets/e9030a38-8d37-4cda-8ad3-e2a9ee01bf9d) ![image](https://github.com/user-attachments/assets/1aee80a7-59f5-42dc-b04e-d550ba835c5b)

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
![image](https://github.com/user-attachments/assets/27f4225f-e16d-44b2-8e84-033098201294)

<br><br>
5. Tom can now review the changes when he logs in and merge the changes as necessary.



<br><br>

**Next:** [Lab 7: Collaborative Workflows](07_collaborative_workflows.md)



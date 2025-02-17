***"Success doesn't come from what you do occasionally. It comes from what you do consistently." – Marie Forleo***
<br><br>

# Lab 9: Git Forking
![image](https://github.com/user-attachments/assets/77066e2e-a55f-4c59-b6ee-3bdeecf8f8a1)

>This creates a cloned copy of the original repository, when you are not part of a project,
>but it's a place where you can operate on it safely.  You can then do a pull request once
>you have made some contributions to the project.

<br><br>
# Main Lab
![image](https://github.com/user-attachments/assets/a3487228-d0f1-4665-a175-50b8c6eae2c3)
![image](https://github.com/user-attachments/assets/32853b67-4bbe-4319-9b9b-4972e5a0bc17)
![image](https://github.com/user-attachments/assets/550d4f36-0f70-4458-a5d8-088ba9c0958f)
> Jon has Read permissions...so Jon can fork the repo for now.

![image](https://github.com/user-attachments/assets/7d6b8005-a631-4b7a-a5c2-777ea9fc1e76)

> Here you would click `Fork`:
![image](https://github.com/user-attachments/assets/b8d49b30-ccfc-4819-8359-8960e794e72b)

![image](https://github.com/user-attachments/assets/21ff6a8e-b1e4-427f-8ac5-24b6f9f68cf9)

![image](https://github.com/user-attachments/assets/d3aadaa2-4e16-4833-8db6-7c01c3d8a821)

![image](https://github.com/user-attachments/assets/c583b095-5a4c-42f7-9247-7acdfdc0d5e9)

![image](https://github.com/user-attachments/assets/69e425b7-50d4-4088-ae34-05dd2cae8e69)

1. First, `git clone` the newly forked repository:
```
cd /home/jon/; git clone http://git.example.com/jon/story-blog.git
```
![image](https://github.com/user-attachments/assets/21e829e2-39bb-4922-8c98-4f88b10b8b99)

2. Now Jon makes some changes to the Fox and Grapes Story:
```
cat << EOF > fox-and-grapes.txt
--------------------------------------------
      THE FOX AND GRAPES
--------------------------------------------

A Fox one day spied a beautiful bunch of ripe grapes hanging from a vine trained along the branches of a tree.

The grapes seemed ready to burst with juice, and the Fox's mouth watered as he gazed longingly at them.

The bunch hung from a high branch, and the Fox had to jump for it.

The first time he jumped he missed it by a long way.

So he walked off a short distance and took a running leap at it, only to fall short once more.

Again and again he tried, but in vain.

Now he sat down and looked at the grapes in disgust.

"What a fool I am," he said. "Here I am wearing myself out to get a bunch of sour grapes that are not worth gaping for."

And off he walked very, very scornfully.
EOF
```

3. Stage and commit the new changes.  Then push them to the remote master:
![image](https://github.com/user-attachments/assets/aa07b53d-d4b8-4b45-bea8-522475f820d0)

![image](https://github.com/user-attachments/assets/172832fa-3f3a-4b00-8a32-664df4afd95a)
```
git add fox-and-grapes.txt
git commit -m "Added fox-and-grapes story"
git push -u origin master
```

4. Submit a Pull Request to merge changes to Sarah's repository:

![image](https://github.com/user-attachments/assets/ab8b1ebb-bb88-487a-9e45-d0bd2333a1d0)

![image](https://github.com/user-attachments/assets/74689523-9604-4572-81d6-a636f5109124)

![image](https://github.com/user-attachments/assets/1b4e14e2-ac93-4332-8d4a-131244c324c9)

![image](https://github.com/user-attachments/assets/1711cc3f-0fd0-4a86-8af3-b8469c617acb)

5. Log in as Sarah to approve the merge:
![image](https://github.com/user-attachments/assets/b7f09f6a-56e3-442b-a3fb-b04ecec85f84)

![image](https://github.com/user-attachments/assets/d7de3eb0-ae68-4a30-95ee-f3a7ec047310)

> Click on the Notifications to view the PR:

![image](https://github.com/user-attachments/assets/0187bd4d-003b-4aed-8284-c16966cd4726)

![image](https://github.com/user-attachments/assets/308f84d4-cb86-48cd-9b06-9235821d2a6b)
> Merge Pull Request


<br><br>
**Next:** [Lab 10: Custom Configurations](10_custom_configurations.md)



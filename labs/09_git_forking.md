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



<br><br>
**Next:** [Lab 10: Custom Configurations](10_custom_configurations.md)



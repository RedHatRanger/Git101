***"You can’t go back and change the beginning, but you can start where you are and change the ending." – C.S. Lewis***
<br><br>

# Lab 10: Git Rebasing
![image](https://github.com/user-attachments/assets/7b6f275c-acdb-446b-86ce-f8ac136c829f)

![image](https://github.com/user-attachments/assets/032155ca-7116-4473-89ca-02e517f5d6d6)

<br><br>
>However, another way to achieve this is through REBASING:

![image](https://github.com/user-attachments/assets/66879c3b-e506-4faa-8026-2b8643b37d49)

<br><br>
>You can also rebase INTERACTIVELY:

![image](https://github.com/user-attachments/assets/fb2f67c2-5f32-4b49-a4fc-0e06d6cb01ea)

![image](https://github.com/user-attachments/assets/9d5c70fb-9808-4f84-815c-cdac7af067c0)

![image](https://github.com/user-attachments/assets/05896623-c213-4a44-935f-39c21fdebcdb)

![image](https://github.com/user-attachments/assets/3771dc69-6002-4caf-a9a1-b85d0e6eb95f)

>Here, we successfully created a new commit that contains all the changes of the last 4 commits!


># The Setup
```
cd ~/story-blog
cat << EOF > wolf-and-goat.txt
--------------------------------------------
      THE WOLF AND THE GOAT
--------------------------------------------

A wolf saw a goat grazing at the edge of a high cliff. The wolf smacked his lips at the thought of a fine goat dinner.

"My dear friend," said the wolf in his sweetest voice, "aren't you afraid you will fall down from that cliff? Come down here and graze on this fine grass beside me on safe, level ground."

"No, thank you," said the goat.

"Well then," said the wolf, "aren't you cold up there in the wind? You would be warmer grazing down here beside me in this sheltered area."

"No, thank you," said the goat.

"But the grass tastes better down here!" said the exasperated wolf, "Why dine alone?"

"My dear wolf," the goat finally said, "are you quite sure that it is MY dinner you are worrying about and not your own?"
<br><br>
EOF

cat << EOF > hare-and-tortoise.txt
--------------------------------------------
      THE HARE AND TORTOISE
--------------------------------------------

A Hare was making fun of the Tortoise one day for being so slow.

"Do you ever get anywhere?" he asked with a mocking laugh.

"Yes," replied the Tortoise, "and I get there sooner than you think. I'll run you a race and prove it."

The Hare was much amused at the idea of running a race with the Tortoise, but for the fun of the thing he agreed.

So the Fox, who had consented to act as judge, marked the distance and started the runners off.

The Hare was soon far out of sight, and to make the Tortoise feel very deeply how ridiculous it was for him to try a race with a Hare, he lay down beside the course to take a nap until the Tortoise should catch up.

The Tortoise meanwhile kept going slowly but steadily, and, after a time, passed the place where the Hare was sleeping.

But the Hare slept on very peacefully; and when at last he did wake up, the Tortoise was near the goal. The Hare now ran his swiftest, but he could not overtake the Tortoise in time.
EOF
```



<br><br>
# Main Lab
![image](https://github.com/user-attachments/assets/c46274ad-5879-4a4b-8438-194a712ff010)

![image](https://github.com/user-attachments/assets/5579f4e3-0338-4f61-9619-a20476c156f9)

![image](https://github.com/user-attachments/assets/63155186-2e62-4111-b085-4827c87d0e61)

<br><br>
1. Let's pull the changes from the remote repository:
![image](https://github.com/user-attachments/assets/46ded33d-b969-48c7-ae86-82cff81a83e4)

```
cd ~/story-blog
git checkout master
git pull origin master
```
![image](https://github.com/user-attachments/assets/2d31fdd9-943e-4cdf-9f22-e83d51d94f69)

![image](https://github.com/user-attachments/assets/73623d30-fb2c-4b4f-a2a8-67950a778262)

<br><br>
2. How many commits are in the `story/hare-and-tortoise`:
```
git log story/tortoise-and-hare
```
![image](https://github.com/user-attachments/assets/17622785-0017-4318-b495-a6c9c86afa75)

>Answer: 5

<br><br>
3. Rebase the `story/hare-and-tortoise` branch on top of `master`:
![image](https://github.com/user-attachments/assets/de3c9f52-d9aa-449f-86bf-8bf7a543dd27)

```
git checkout story/hare-and-tortoise
git rebase master
```

![image](https://github.com/user-attachments/assets/e3c36427-0e00-4c48-85e7-16b94b7648f7)


![image](https://github.com/user-attachments/assets/904418e6-23f1-42db-bfaf-17291de48721)

![image](https://github.com/user-attachments/assets/8851a8ce-dddc-42cc-8d54-6504bb20b70b)

```
git log --oneline
git rebase -i HEAD~3

# squash the bottom two commits by replacing pick with squash. Then save the file.

git log --oneline
```
![image](https://github.com/user-attachments/assets/4b1b2efe-0146-4330-99be-252e0bde8cd0)

![image](https://github.com/user-attachments/assets/4b7d081a-0393-40e2-be49-edb89851ffd6)

*

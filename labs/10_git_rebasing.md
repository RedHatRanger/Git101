
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





























***"You can’t go back and change the beginning, but you can start where you are and change the ending." – C.S. Lewis***
<br><br>

# Lab 10: Git Rebasing (5th Grader Edition)

![image](https://github.com/user-attachments/assets/7b6f275c-acdb-446b-86ce-f8ac136c829f)
![image](https://github.com/user-attachments/assets/032155ca-7116-4473-89ca-02e517f5d6d6)
![image](https://github.com/user-attachments/assets/66879c3b-e506-4faa-8026-2b8643b37d49)

## Quick Review of Previous Labs
- **Lab 1**: We set up Git and learned to make our first commits.
- **Lab 2**: We created branches so we could work on new stories without messing up the main code.
- **Lab 3**: We merged those branches back into the main.
- **Lab 4**: We pushed our code to a remote and learned to pull.
- **Lab 5**: We cloned someone’s repo to our computer.
- **Lab 6**: We made Pull Requests to share our changes.
- **Lab 7**: We fetched and pulled to stay in sync with the remote.
- **Lab 8**: We handled merge conflicts when two people changed the same line.
- **Lab 9**: We forked a project to make our own copy.

Now, in **Lab 10**, we’ll explore **Git Rebasing**. Rebasing is like **rewriting the order** of your commits so your story timeline looks neat. It can help you make your commits look like they happened in a smoother order, rather than lots of jumps.

---

## Why Rebase?
Sometimes, you have a bunch of commits that fix small mistakes or reorder your changes. **Rebasing** can tidy them up so it looks like you wrote your code perfectly the first time. It also helps keep your main branch’s history clear.

Think of it as taking pages out of order in a book and lining them up so the story flows better.

---

## The Setup
We have two new story files: **wolf-and-goat.txt** and **hare-and-tortoise.txt**. We’ll pretend these commits are scattered or out of order, and we want to **rebase** them.

```bash
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

>We just wrote two new fables. We’ll commit them in a branch and then learn how to reorder or squash commits with **rebase**.

## Set Up Multiple Commits to Squash
Imagine you keep editing `hare-and-tortoise.txt` in small steps. Here’s how to create **3 separate commits** before squashing them:

```bash
cd ~/story-blog
git checkout -b story/hare-and-tortoise



# 1st change
echo "The Hare bragged a bit about his speed." >> hare-and-tortoise.txt

# Stage 1st change and commit
git add hare-and-tortoise.txt
git commit -m "Commit 1: hare boasting"



# 2nd change
echo "The Tortoise yawned and said 'We’ll see, dear Hare.'" >> hare-and-tortoise.txt

# Stage 2nd change and commit
git add hare-and-tortoise.txt
git commit -m "Commit 2: tortoise line"



# 3rd change
echo "A crowd of forest animals came to watch." >> hare-and-tortoise.txt

# Stage 3rd change and commit
git add hare-and-tortoise.txt
git commit -m "Commit 3: forest animals"
```

Now you have 3 commits in this branch. Let’s see how to squash them:

### Squashing the 3 Commits
```bash
git rebase -i HEAD~3
```

1. A file opens with lines like:
   ```
   pick abcd123 Commit 1: hare boasting
   pick efgh456 Commit 2: tortoise line
   pick ijkl789 Commit 3: forest animals
   ```
2. Change the second and third “pick” to “squash,” like:
   ```
   pick abcd123 Commit 1: hare boasting
   squash efgh456 Commit 2: tortoise line
   squash ijkl789 Commit 3: forest animals
   ```
3. Save and exit. Git will combine all three commits into **one**. You can also update the commit message.

That’s it—your commit history is now tidier!

1. **Rebase**: Moves your commits to start after the main branch’s tip, keeping your timeline straight.
2. **Interactive Rebase**: Lets you reorder or squash commits.
3. **Why?** So your history looks clean and easy to read.

Rebasing is optional, but it’s a powerful way to keep your story (Git history) from getting confusing. Nice job exploring how to reorder commits!

---

**Next**: [Lab 11: Git Cherry-Picking](11_git_cherry_picking.md)

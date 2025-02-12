***"Talk is cheap. Show me the code." — Linus Torvalds***
<br><br>


# Lab 2: Git Branches
![image](https://github.com/user-attachments/assets/5e5c7023-217e-4c5c-812a-ff06092eefdc) ![image](https://github.com/user-attachments/assets/74f1d8d4-f126-4c48-ad65-a6b557cb9b00) ![image](https://github.com/user-attachments/assets/e8eb3868-d91f-48b6-84dc-2c0d86694390) ![image](https://github.com/user-attachments/assets/13124f19-b9fa-4330-a545-7869ae9f43fb) ![image](https://github.com/user-attachments/assets/15409879-112b-4aa3-916e-9ec9357f7ecb) ![image](https://github.com/user-attachments/assets/fca6afe7-a819-4980-a4eb-53d8d022ac1b) ![image](https://github.com/user-attachments/assets/9e7ffaf2-1372-4d69-9016-472b09d2a426) ![image](https://github.com/user-attachments/assets/1042e3c6-cbf2-47ce-a627-9977eea6939a) ![image](https://github.com/user-attachments/assets/687bfd05-3178-4e36-9c93-7379bcf5e6e6) ![image](https://github.com/user-attachments/assets/eca726ae-f05d-478e-8d96-87d9a81e1a0e) ![image](https://github.com/user-attachments/assets/0dabc748-1923-4220-bea0-66492e1ea28e)

(photos by: kodekloud.com)

<br><br><br><br>
### What is a Git Branch?
- A ***Git branch*** is a movable pointer to a specific commit, i.e. it allows you develop features and fixes independently from the main codebase (master branch).


## Objectives

1. Create and switch between branches
2. Understand best practices for branch naming
3. Merge simple changes back into the main branch
4. Resolve basic merge conflicts

<br><br><br><br>

```
cd Projects/story-blog
git log --name-only
# You should see lion-and-mouse.txt




# Let's prepare the lab for the lion-and-mouse.txt:
cat << EOF > lion-and-mouse.txt
--------------------------------------------
      THE LIOON AND THE MOUSE
--------------------------------------------

A Lion lay asleep in the forest, his great head resting on his paws.

A timid little Mouse came upon him unexpectedly, and in her fright and haste to get away, ran across the Lion's nose.

Roused from his nap, the Lion laid his huge paw angrily on the tiny creature to kill her.

"Spare me!" begged the poor Mouse. "Please let me go and some day I will surely repay you."

The Lion was much amused to think that a Mouse could ever help him. But he was generous and finally let the Mouse go.

Some days later, while stalking his prey in the forest, the Lion was caught in the toils of a hunter's net.

Unable to free himself, he filled the forest with his angry roaring.

The Mouse knew the voice and quickly found the Lion struggling in the net.

Running to one of the great ropes that bound him, she gnawed it until it parted, and soon the Lion was free.

"You laughed when I said I would repay you," said the Mouse. "Now you see that even a Mouse can help a Lion."
EOF




#Let's create and switch to a new branch "story/frogs-and-ox":
git checkout -b story/frogs-and-ox




# Use git log to see where the HEAD is pointing now:
git log
# You can see the HEAD is now pointing to the new branch story/frogs-and-ox




# Let's add the frogs-and-ox.txt:
cat << EOF > frogs-and-ox.txt
--------------------------------------------
      THE FROGS AND THE OX
--------------------------------------------

An Ox came down to a reedy pool to drink. As he splashed heavily into the water, he crushed a young Frog into the mud.

The old Frog soon missed the little one and asked his brothers and sisters what had become of him.

"A great big monster," said one of them, "stepped on little brother with one of his huge feet!"

"Big, was he!" said the old Frog, puffing herself up. "Was he as big as this?"

"Oh, much ...."
EOF




# Uh oh...Max calls and interrupts the development...we need to stage and commit the incomplete story to the master branch:
git add frogs-and-ox.txt
git commit -m "Add incomplete frogs-and-ox story"




# Now, let's switch to the master branch:
git checkout master





```

## I. Creating a Branch

1. View current branches:
   ```bash
   git branch
   ```

2. Create a new branch and switch to it:
```bash
git branch feature/login
git checkout feature/login
```
Alternatively:
```bash
git checkout -b feature/login
```

<br><br>

## II. Making Changes on a Branch
1. Add or edit files related to your new feature:
```bash
echo "Login feature code" > login.md
```

2. Stage and commit:
```bash
git add login.md
git commit -m "Implement basic login feature"
```

<br><br>

## III. Merging into Main (or Master)
1. Switch back to your main branch:
```bash
git checkout main
```

2. Merge the feature branch:
```bash
git merge feature/login
```

3. View your history to see the merge commit:
```bash
git log --oneline --graph
```

<br><br>

## IV. Handling Simple Conflicts
1. If you have conflicting changes, Git will show conflict markers in your files.
2. Open the file, decide which changes to keep (or combine them), remove the conflict markers, then:
```bash
git add <conflicted-file>
git commit
```

<br><br>

## Summary
Branching allows parallel development without disrupting the main codebase. In the next labs, we’ll dig into more advanced branching and merging strategies.

<br><br>

**Next:** Lab 3: Working with Remotes



<br><br><br><br>
### In case you missed any of the previous labs, here are the commands we ran to setup it all up:
1. [Install Git](https://github.com/RedHatRanger/Git101/blob/main/labs/01_git_setup_and_basic_workflows.md#i-install-git) (if you haven't already)
2. Copy and paste the rest below to your terminal:

```bash
# Lab 1:
git config --global user.name "RedHatRanger"
git config --global user.email "RedHatRanger@example.com"
mkdir -p Projects/story-blog
cd Projects/story-blog
echo "This is a beautiful story" > story1.txt
echo "A Lion lay asleep in the forest" > lion-and-mouse.txt
echo "story1.txt" > .gitignore
git status
git add lion-and-mouse.txt
git commit -m "Add the lion and mouse story"
git log
git log --oneline
echo "Some notes about Git" > notes.md
git add notes.md
git commit -m "Add notes on Git"
```

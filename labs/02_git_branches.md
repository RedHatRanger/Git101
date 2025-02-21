***"Talk is cheap. Show me the code." — Linus Torvalds***
<br><br>

# Lab 2: Git Branches (5th Grader Edition)

![image](https://github.com/user-attachments/assets/5e5c7023-217e-4c5c-812a-ff06092eefdc)
![image](https://github.com/user-attachments/assets/74f1d8d4-f126-4c48-ad65-a6b557cb9b00)
![image](https://github.com/user-attachments/assets/e8eb3868-d91f-48b6-84dc-2c0d86694390)
![image](https://github.com/user-attachments/assets/13124f19-b9fa-4330-a545-7869ae9f43fb)
![image](https://github.com/user-attachments/assets/15409879-112b-4aa3-916e-9ec9357f7ecb)
![image](https://github.com/user-attachments/assets/fca6afe7-a819-4980-a4eb-53d8d022ac1b)
![image](https://github.com/user-attachments/assets/9e7ffaf2-1372-4d69-9016-472b09d2a426)
![image](https://github.com/user-attachments/assets/1042e3c6-cbf2-47ce-a627-9977eea6939a)
![image](https://github.com/user-attachments/assets/687bfd05-3178-4e36-9c93-7379bcf5e6e6)
![image](https://github.com/user-attachments/assets/eca726ae-f05d-478e-8d96-87d9a81e1a0e)
![image](https://github.com/user-attachments/assets/0dabc748-1923-4220-bea0-66492e1ea28e)

(photos by: kodekloud.com)

---

## Quick Review of Previous Lab
- In **Lab 1**, we set up Git, learned how to make commits, and track changes to our files.
- In **Lab 2**, we’ll learn about **branches**—like creating different storylines so we don’t mess up the main story if we make a mistake or want to experiment.

<br><br>
## What is a Git Branch?
Think of a Git branch like a **fork** in a road. Instead of everybody walking on the same path, you can explore a different path and come back to join the main road later, **without messing up** what’s happening on the main road. This is super helpful when you want to test new ideas or fix something without breaking everything!

---

## Why Use Branches?
- **Safety**: You can experiment on a side path and not worry about breaking the main project.
- **Teamwork**: Everyone can work on their own path (branch) at the same time.
- **History**: You can always see how or why something changed.

---

## Objectives
1. **Create and switch between branches**
2. **Give your branches good names** so you don’t get confused.
3. **Merge** what you did on your branch back into the main project.
4. **Fix conflicts** when two branches have different ideas.

---


<br><br><br><br>
# Main Lab

```bash
mkdir -p Projects/story-blog
mkdir -p Projects/website
cd Projects/story-blog


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


# Setup the main.html file:
cat << EOF > ../website/main.html
main-placeholder
EOF


git log --name-only
# You should see lion-and-mouse.txt


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

# Let's fix the misspelled "LIOON" in the lion-and-mouse.txt:
sed -i 's/LIOON/LION/g' lion-and-mouse.txt

# Commit the changes to the master:
git add lion-and-mouse.txt; git commit -m "Fix typo in story title"

# Switch back to the /frogs-and-ox branch
git checkout story/frogs-and-ox

# Sarah has now finished her incomplete story:
cat << EOF > frogs-and-ox.txt
--------------------------------------------
      THE FROGS AND THE OX
--------------------------------------------

An Ox came down to a reedy pool to drink. As he splashed heavily into the water, he crushed a young Frog into the mud.

The old Frog soon missed the little one and asked his brothers and sisters what had become of him.

"A great big monster," said one of them, "stepped on little brother with one of his huge feet!"

"Big, was he!" said the old Frog, puffing herself up. "Was he as big as this?"

"Oh, much bigger!" they cried.

The Frog puffed up still more.

"He could not have been bigger than this," she said.

But the little Frogs all declared that the monster was much, much bigger and the old Frog kept puffing herself out more and more until, all at once, she burst.
EOF


# Commit the new changes:
git add frogs-and-ox.txt; git commit -m "Completed frogs-and-ox story"


# Next one:
cd ../website
git init
git branch feature/cart
git branch feature/checkout
git branch feature/signout
git branch feature/signup
git checkout feature/signout; git log --graph --decorate
```

### What’s Happening?
1. You make **a new branch** (`story/frogs-and-ox`) to write another story.
2. You **realize** you left the first story incomplete, so you commit your partial changes.
3. You **switch back** to `master` (the main road) and fix a typo.
4. You jump **back** to your branch and **finish** your new story.
5. Finally, you create and look at **other branches** in the `../website` folder.

---

## I. Creating a Branch (Simplified)
Imagine you have a main path called `main` or `master`. To start a new path:

```bash
git branch feature/login
# Make a new branch (a new path)

git checkout feature/login
# Walk down that new path

# Or do both at once:
git checkout -b feature/login
```

---

## II. Making Changes on a Branch
You can do anything you want on your new path without touching the main path.

```bash
echo "Login feature code" > login.md

# Save changes

git add login.md

git commit -m "Implement basic login feature"
# Put your changes into your local Git history
```

---

## III. Merging Back into Main
After you finish your changes, you can walk back to the main path and merge your updates.

```bash
git checkout main
# Return to main branch

git merge feature/login
# Merge your feature changes in

# Check what the history looks like:
git log --oneline --graph
```

---

## IV. Handling Simple Conflicts
Sometimes two different paths conflict. If both changed the same line, Git will **stop** and ask you to fix it.

```bash
# Open the file with conflicts.
# Look for lines like <<<<<<< and >>>>>>>
# Decide how the final text should look.
# Then stage and commit.

git add <conflicted-file>
git commit -m "<commit_message>"
```

---

## The Big Idea
Branches let you do your own thing without messing up other things. When you’re ready, you **merge** it back in. If there’s a fight (a conflict), you fix it by deciding how the combined code should look.

That’s it! You’re branching like a pro, even in 5th grade.


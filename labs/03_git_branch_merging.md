***"The people who are crazy enough to think they can change the world, are the ones who do." – Steve Jobs***
<br><br>


# Lab 3: Git Branch Merging
![image](https://github.com/user-attachments/assets/96f8b44f-7075-47b9-a7ac-386407474fd9) ![image](https://github.com/user-attachments/assets/073d11f1-f7d7-4c5b-87aa-acc8de59a32c) ![image](https://github.com/user-attachments/assets/eb99e756-4957-4df7-8118-b4c72041ceed) ![image](https://github.com/user-attachments/assets/b9e58837-9866-4150-8db0-aef1a08b64b9) ![image](https://github.com/user-attachments/assets/42a359c2-14a2-4895-80aa-7473f4366fd7) ![image](https://github.com/user-attachments/assets/ef80e53d-b661-4295-9518-7961cba71d47) 


# Switch back to master branch:
```
git checkout master
```

# How many branches?  There are two:
```
git branch
# Output:
# * master
#   story/frogs-and-ox
```

# Let's check git log:
```
# The new story Sarah wrote is in the story/frogs-and-ox branch. It's time to merge the branch and bring it to the master branch.
# But before that look at the log of the master and story/frogs-and-ox branches and identify how many commits there have been in the past on each branch.

git log master
git log story/frogs-and-ox
```

# Time to merge the `story/frogs-and-ox` branch with `master`:
```
git merge story/frogs-and-ox -m "Merge branch 'story/frogs-and-ox'"
```




## Summary
Branching allows parallel development without disrupting the main codebase. In the next labs, we’ll dig into more advanced branching and merging strategies.

<br><br>

**Next:** [Lab 3: Merging Branches](03_git_branch_merging.md)



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


# Lab 2
mkdir -p Projects/website
cd Projects/story-blog

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

cat << EOF > ../website/main.html 
main-placeholder
EOF

git log --name-only
git checkout -b story/frogs-and-ox
git log
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

git add frogs-and-ox.txt
git commit -m "Add incomplete frogs-and-ox story"
git checkout master
sed -i 's/LIOON/LION/g' lion-and-mouse.txt
git add lion-and-mouse.txt; git commit -m "Fix typo in story title"
git checkout story/frogs-and-ox
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

git add frogs-and-ox.txt; git commit -m "Completed frogs-and-ox story"
cd ../website
git init
git branch feature/cart
git branch feature/checkout
git branch feature/signout
git branch feature/signup
git checkout feature/signout; git log --graph --decorate
git branch
git branch feature/login
git checkout feature/login
git checkout -b feature/login
echo "Login feature code" > login.md
git add login.md
git commit -m "Implement basic login feature"
git merge feature/login
```

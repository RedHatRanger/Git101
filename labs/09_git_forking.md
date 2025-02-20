***"Success doesn't come from what you do occasionally. It comes from what you do consistently." – Marie Forleo***
<br><br>

# Lab 9: Git Forking (5th Grader Edition)
![image](https://github.com/user-attachments/assets/77066e2e-a55f-4c59-b6ee-3bdeecf8f8a1)

## Quick Review of Previous Labs

- **Lab 1**: We learned how to set up Git and make our first commits.
- **Lab 2**: We created new branches so we could work on extra stories without messing up the main code.
- **Lab 3**: We merged those branches back into the main.
- **Lab 4**: We pushed our code to a remote and learned to pull changes.
- **Lab 5**: We cloned (copied) a remote repository to our computer.
- **Lab 6**: We made Pull Requests so others could review our changes.
- **Lab 7**: We fetched and pulled updates from the remote to stay in sync.
- **Lab 8**: We handled merge conflicts when two people changed the same line.

Now, in **Lab 9**, we’ll learn about **forking**. This is like taking someone else’s project and making your own **private copy**, so you can change it however you want—without breaking their original.

---

## Why Fork?

Sometimes, you aren’t part of a project, but you still want to make changes. **Forking** copies the original repo into **your** account. Then you can do your own work and, if you like, make a Pull Request to share your improvements back with the project owner.

Think of it like borrowing someone’s storybook. You photocopy it (fork) and add your own chapter to the copy. Later, you can show the new chapter to the story’s original author.

---

## Lab Setup: Where We’ll Fork

1. **Sarah’s Repository**: Suppose Sarah has a repo called `story-blog` on GitHub. But your friend Jon only has **read** permissions.
2. **Jon** wants to add a new story (`fox-and-grapes.txt`) but can’t push directly to Sarah’s repo.
3. **So** Jon will **fork** Sarah’s `story-blog`, create a new branch, and eventually open a Pull Request for Sarah to review.

---

## Main Lab

### 1. Fork the Repo

1. On Sarah’s `story-blog` GitHub page, click the **Fork** button.
2. Pick your own account (like `jon/story-blog`) as the place to copy it.
3. Now you have **your own** version of `story-blog`!

> **Kid-Friendly**: It’s like making a copy of Sarah’s story and putting it in **your** bookshelf.

### 2. Clone Your Fork

```bash
cd /home/jon/
git clone http://git.example.com/jon/story-blog.git
```

This puts **your** copy of the repo on your computer.

### 3. Add the “Fox and Grapes” Story

```bash
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


git add fox-and-grapes.txt
git commit -m "Added fox-and-grapes story"
git push -u origin master
```

Now your new story is on **your** fork’s `master` branch.

### 4. Pull Request to Original Repo

1. Go back to GitHub. In your fork (`jon/story-blog`), click **Pull Request**.
2. Choose the **source** (`jon/story-blog`), and the **destination** (Sarah’s `story-blog`).
3. Give it a title (e.g., “Added fox-and-grapes story”).
4. Submit your Pull Request.

> **Kid-Friendly**: You’re saying, “Hey Sarah, I made a new story. Want to add it to your main book?”

### 5. Sarah Reviews and Merges

Sarah sees your Pull Request:

- She reads your changes.
- She can approve or ask questions.
- If everything looks good, she **merges** your work into `story-blog`.

Now your story is part of Sarah’s original repo!

---

## Summary

1. **Fork**: Make your own copy of someone else’s project.
2. **Clone** your fork so you can edit on your computer.
3. **Push** changes to your fork (not Sarah’s original).
4. **Pull Request** if you want your work added to the original.

Forking is super handy for open-source projects, or any time you want to try something new in someone else’s repository without messing up their work. Nice job exploring Git forks!

---

**Next**: [Lab 10: Git Rebasing](10_git_rebasing.md)


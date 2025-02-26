***"Success is a journey, not a destination." – Arthur Ashe*** 
<br><br>

# Lab 16: Custom Configurations (5th Grader Edition)

## Quick Review of Previous Labs
- **Lab 1**: We learned Git basics and made our first commits.
- **Lab 2**: We created branches to test new stories.
- **Lab 3**: We merged those branches back.
- **Lab 4**: We learned to push and pull with a remote.
- **Lab 5**: We cloned a remote project to our computer.
- **Lab 6**: We made Pull Requests to share changes.
- **Lab 7**: We fetched and pulled updates.
- **Lab 8**: We handled merge conflicts.
- **Lab 9**: We forked a project.
- **Lab 10**: We rebased commits for a tidy timeline.
- **Lab 11**: We cherry-picked a single commit.
- **Lab 12**: We reset or reverted mistakes.
- **Lab 13**: We stashed changes to save them for later.
- **Lab 14**: We used Reflog to recover "lost" commits.
- **Lab 15**: We peeked under Git’s hood with plumbing commands.

**Now**, in **Lab 16**, we’ll learn how to **customize** Git so it feels like **your** own. We’ll look at **aliases**, **hooks**, and a **global .gitignore**—all ways to make Git do more of what **you** want.

---
<br><br>
## Why Custom Configurations?
Git offers **lots** of ways to make your coding life easier:
- **Aliases**: Shortcuts for your favorite commands.
- **Hooks**: Automate tasks like running tests or checking code style.
- **Global .gitignore**: Skip certain files for **all** your projects.

Think of it like decorating your room so you can do your homework more comfortably!

---

<br><br>
## Objectives
1. **Define useful Git aliases** (shortcuts).
2. **Explore Git hooks** (automatic tasks).
3. **Set up a global .gitignore** (always ignore certain files).

---

<br><br>
## Setup: Checking Your Current Git Settings
1. **See your current config**:
   ```bash
   git config --list
   ```
   This shows your user name, email, and possibly some aliases or ignore files.
2. **Decide** if you want to set up aliases/hook examples in your global config or just in this project. For lab practice, you can do them locally.

---

<br><br>
## I. Git Aliases

Git aliases let you **rename** commands to shorter words.

### Example
```bash
git config --global alias.co checkout
# Now 'git co' = 'git checkout'

git config --global alias.st status
# 'git st' = 'git status'

git config --global alias.cm "commit -m"
# 'git cm "message"' = 'git commit -m "message"'
```

It’s like calling your friend "Ben" instead of "Benjamin." Same person, shorter name!

Now you can use `git co`, `git st`, and `git cm "..."` instead of typing the full commands.

---

<br><br>
## II. Git Hooks

Hooks are little scripts that Git runs when **certain events happen**:
- `pre-commit`: runs **before** you commit.
- `post-commit`: runs **after** you commit.
- etc.

### Example: A Pre-Commit Hook
1. In your repo, go to `.git/hooks/`.
2. There’s a sample called `pre-commit.sample`. Rename it to `pre-commit`.
3. Make it executable:
   ```bash
   chmod +x .git/hooks/pre-commit
   ```
4. Add commands inside that file, like a small test or `echo "Check your code!"`.

It’s like a "to-do note" that always runs before you close your notebook.

---

<br><br>
## III. Global .gitignore

Sometimes you want Git to **always** ignore certain files (like OS files: `.DS_Store` on Mac, or `Thumbs.db` on Windows) in **all** your projects.

### Step 1: Create a Global Ignore File
```bash
git config --global core.excludesfile ~/.gitignore_global
```

### Step 2: Add Patterns to `.gitignore_global`
```bash
echo ".DS_Store" >> ~/.gitignore_global
echo "Thumbs.db" >> ~/.gitignore_global
```

Now Git will skip these in every repo you work on.

**Kid-Friendly**: It’s like telling your teacher "Ignore all doodles on the back of my pages!" for every assignment.

---

<br><br>
## Summary
- **Aliases** save time by letting you type shortcuts.
- **Hooks** automate tasks (like tests) when you commit.
- **Global .gitignore** ensures certain files are **always** ignored.

With these custom configurations, Git becomes even more friendly and powerful—just the way **you** like it!

---

<br><br>
**Next**: [Lab 17: Git Troubleshooting](17_git_troubleshooting.md)

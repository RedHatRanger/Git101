***"Neither comprehension nor learning can take place in an atmosphere of anxiety." – Rose Kennedy***
<br><br>

# Lab 17: Git Troubleshooting (5th Grader Edition)

## Quick Review of Previous Labs
- **Lab 1**: We learned Git basics and made our first commits.
- **Lab 2**: We created branches to test new stories.
- **Lab 3**: We merged those branches back.
- **Lab 4**: We learned to push and pull with a remote.
- **Lab 5**: We cloned a remote project onto our computer.
- **Lab 6**: We made Pull Requests to share changes.
- **Lab 7**: We fetched and pulled updates.
- **Lab 8**: We handled merge conflicts.
- **Lab 9**: We forked a project.
- **Lab 10**: We rebased commits for a tidy timeline.
- **Lab 11**: We cherry-picked a single commit.
- **Lab 12**: We reset or reverted mistakes.
- **Lab 13**: We stashed changes to save them for later.
- **Lab 14**: We used Reflog to recover “lost” commits.
- **Lab 15**: We explored Git’s plumbing commands.
- **Lab 16**: We set up custom configurations (aliases, hooks, etc.).

Now, in **Lab 17**, we’ll learn common **troubleshooting** tips for Git—so you know how to fix everyday hiccups, from removing branches to dealing with “Why won’t Git let me push?”

---

<br><br>
## Why Troubleshoot?
Sometimes, Git does something you don’t expect. Maybe a branch is stuck, or you can’t push your changes. These **tips** help you fix your code quickly, so you can get back to having fun.

It’s like having a first aid kit for your code.

---

<br><br>
## Common Git Troubles

### 1. Removing a Branch

If you want to clean up old branches:

**Remove a local branch** from your machine:
```bash
git branch -d <local_branch>
# Use -D to force-delete if it won't let you.
```

**Remove a remote branch** from the server:
```bash
git push origin -d <remote_branch>
```

Imagine your story has finished, so you throw away that side path.

---

<br><br>
### 2. “It Won’t Let Me Push!”

**Symptom**: You run `git push`, but Git says there’s new stuff on the remote you don’t have.

**Fix**:
1. Run `git pull --rebase origin main` (or whatever branch name) to get their changes.
2. Resolve any conflicts.
3. Try pushing again.

**Kid-Friendly**: It’s like your friend updated a shared story, so you need their new pages before adding yours.

---

<br><br>
### 3. “I Committed on the Wrong Branch!”

**Symptom**: You realized you were on `main` but wanted a new branch.

**Fix**:
1. Make a branch from **before** that commit:
   ```bash
   git checkout -b fix/my-branch HEAD~1
   ```
2. Move your commit to this new branch, or cherry-pick it.
3. Reset main if you want to remove the accidental commit from `main`.
Oops, you wrote your new story pages in the big master notebook. Copy them to a side notebook, then erase them from the main one.

---

<br><br>
### 4. Can’t Merge Because of Conflicts

**Symptom**: You do `git merge branchX` and Git complains about conflict.

**Fix**:
1. Edit the files to decide which version to keep.
2. Remove the conflict markers (`<<<<<<`, `>>>>>>`).
3. Stage (`git add .`), then commit.

Two kids wrote on the same line. You decide how to combine or pick one.

---

<br><br>
### 5. Lost Commits (Forgot a commit hash?)

**Symptom**: You reset too hard or can’t find your commit.

**Fix**:
1. `git reflog`: shows every move.
2. Find the commit hash in the reflog.
3. `git checkout <hash>` or `git cherry-pick <hash>` to recover.

Reflog is like your detective journal of all changes.

---

<br><br>
## Extra Tips

1. **Check your Git version**:
   ```bash
   git --version
   ```
   If it’s old, updating might fix weird bugs.

2. **Check your Remotes**:
   ```bash
   git remote -v
   ```
   Make sure `origin` points to the right place.

3. **Look at Config**:
   ```bash
   git config --list
   ```
   Maybe your user.name or user.email is set wrong.

4. **When All Else Fails**: Google is your friend! Others probably had the same error messages.

---

<br><br>
## Summary
Troubleshooting Git can feel tricky, but these common fixes help keep your code on track:
- **Remove or tidy branches** when you’re done.
- **Pull or rebase** if Git won’t let you push.
- **Cherry-pick** or reset if you messed up commits.
- **Use reflog** to find lost stuff.

It’s like having a **first aid kit** for your code adventures. Great job learning to solve Git problems!

---

<br><br>
**Next**: [Lab 18: Git Command Glossary](18_git_command_glossary.md)


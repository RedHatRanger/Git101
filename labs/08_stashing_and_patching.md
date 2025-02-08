# Lab 8: Stashing and Patching

Sometimes you need to switch tasks quickly without committing half-finished work. **Lab 8** focuses on Git stash and creating patches.

<br><br>
## Objectives

I. Temporarily save uncommitted changes using `git stash`.
II. Generate and apply Git patches.

<br><br>
## I. Using Git Stash
1. Make changes to a file but don’t commit.
2. Run:
   ```bash
   git stash
   ```
3. Check your stash list:
   ```bash
   git stash list
   ```
4. Work on something else (e.g., switch branches).
5. Reapply your stashed changes:
   ```bash
   git stash pop
   ```
   or
   ```bash
   git stash apply
   ```

<br><br>
## II. Generate and apply Git patches

1. Make some commits on a branch.
2. Generate a patch file:
   ```bash
   git format-patch main --stdout > changes.patch
   ```
3. Apply the patch in another branch:
   ```bash
   git apply changes.patch
   ```

<br><br>
## Summary

Stashing is invaluable for quick context switches, and patches let you share specific changes without giving full branch access. These tools enhance flexibility in your workflow.

<br><br>

**Next:** Lab 9: Git Log, Diff, and History



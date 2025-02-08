# Lab 5: Undoing Changes

Mistakes happen! In **Lab 5**, you'll learn how to revert commits, reset your working directory, and use `git checkout` to restore files.
<br><br>
## Objectives

I. Understand `git revert` for undoing public commits \
II. Use `git reset` for local history manipulations \
III. Restore files to previous versions

<br><br><br><br>

## I. Git Revert

- `git revert <commit-hash>` creates a new commit that undoes the changes from the specified commit.
- Useful for undoing changes in a shared repository **without rewriting history**.

<br><br>
## II. Git Reset

- **Soft reset** (keeps changes staged):
  ```bash
  git reset --soft HEAD~1
  ```

- **Mixed reset** (unstages changes, keeps files modified):
  ```bash
  git reset --mixed HEAD~1
  ```

- **Hard reset** (discards changes permanently):
  ```bash
  git reset --hard HEAD~1
  ```
  Use caution with `--hard`, especially if others have pulled your commits.

<br><br>
## III. Restore files to previous versions

Revert an individual file to the last committed state:
```bash
git checkout -- path/to/file.md
```

<br><br>
## IV. Practice

1. Make a commit, then try reverting it with `git revert`.
2. Make another commit, then try `git reset --soft HEAD~1`.
3. Compare differences using `git diff`.

<br><br>

## Summary

You can now strategically undo or revert changes, whether in a shared environment or your local workspace.

<br><br>
**Next:** (For intermediate-level labs) Lab 6: Advanced Branching & Merging


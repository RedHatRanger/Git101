# Lab 6: Advanced Branching & Merging

Welcome to the intermediate stage! In **Lab 6**, you'll explore rebasing, interactive rebases, and complex merges.

<br><br>

## Objectives

I. Understand what rebasing is and when to use it \
II. Perform interactive rebases to clean up commit history \
III. Resolve complex merge conflicts \
IV. Merge vs. Rebase

<br><br>
## I. Basic Rebase

1. Create two branches from `main`: `feature1` and `feature2`.
2. Make commits on both.
3. Switch to `feature2` and rebase onto `feature1`:
   ```bash
   git checkout feature2
   git rebase feature1
   ```

<br><br>
## II. Interactive Rebase

On your `feature2` branch, run:
```bash
git rebase -i HEAD~3
```

A text editor opens. You can reorder commits, squash them, or edit commit messages. Save and exit to apply the rebase.

<br><br>
## III. Handling Conflicts

During rebase or merge, if conflicts occur:

1. Resolve them manually in the affected files.
2. Stage the resolved files:
   ```bash
   git add .
   ```
3. Continue the rebase:
   ```bash
   git rebase --continue
   ```

<br><br>
## IV. Merge vs. Rebase

- **Merge** preserves all commits but can create extra merge commits.
- **Rebase** produces a linear history but rewrites commits. Be cautious rebasing public branches.

<br><br>
## Summary

Rebasing can clean up history and simplify your commit timeline, especially before merging a feature branch into `main`. However, always coordinate with team members to avoid rewriting shared commits.

<br><br>

**Next:** Lab 7: Collaborative Workflows



# Lab 9: Git Log, Diff, and History

Efficiently navigating your Git history helps you identify changes, authors, and commit messages. **Lab 9** highlights powerful commands like `git log` and `git diff`.

<br><br>
## Objectives

I. Use various `git log` options to filter and format commit history \
II. Compare changes between commits or branches with `git diff` \
III. Search commit messages and authors.

<br><br>
## I. Advanced Git Log Options

```bash
# Show commits in one line with a graph
git log --oneline --graph

# Limit to the last 5 commits
git log -5

# Show commits by a specific author
git log --author="Your Name"
```

<br><br>
## II. Git Diff Basics
```bash
# Compare working directory to the last commit
git diff

# Compare staging area to the last commit
git diff --staged

# Compare two branches
git diff main feature/login
```

<br><br>
## III. Searching Commits

Search by commit message:
```bash
git log --grep="fix bug"
```

Combine with author or date filters to narrow results.

<br><br>

## Summary

Mastering `git log` and `git diff` ensures you can quickly trace who changed what and when, crucial for debugging and team coordination.

<br><br>
**Next:** [Lab 10: Custom Configurations](10_custom_configurations.md)



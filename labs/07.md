# Lab 7: Collaborative Workflows

In **Lab 7**, we’ll dive into branching strategies, forking, pull requests, and code reviews—key elements of collaborative Git workflows.

<br><br>
## Objectives

I. Understand when to fork vs. clone \
II. Create pull requests to propose changes \
III. Conduct code reviews effectively \
IV. Merge changes via pull requests

<br><br>
## I. Forking a Repository

1. On GitHub (or another platform), locate the repository you want to contribute to.
2. Click the "Fork" button to create your own copy.
3. Clone your fork locally:
   ```bash
   git clone https://github.com/<your-username>/<forked-repo>.git
   ```

<br><br>

## II. Creating a Feature Branch

```bash
git checkout -b feature/improve-docs
```

Make your changes, then commit and push:
```bash
git push -u origin feature/improve-docs
```

<br><br>
## III. Opening a Pull Request (PR)

1. On GitHub, go to your fork and switch to the `feature/improve-docs` branch.
2. Click **New pull request**.
3. Compare your branch with the original repository’s `main` branch.
4. Add a descriptive title and summary of your changes.

<br><br>
## IV. Code Reviews and Merging

- Reviewers can comment on lines, suggest changes, and approve.
- Once approved, the PR can be merged.
- Sync your local fork afterward:
  ```bash
  git pull origin main
  ```

<br><br>

## Summary

Collaborative workflows rely on well-defined branching strategies, clear communication, and respectful code review processes. Forking and pull requests streamline open-source and team collaboration.

<br><br>
**Next:** Lab 8: Stashing and Patching


# Lab 10: Custom Configurations

Git offers extensive customization options. In **Lab 10**, learn how to set up aliases, hooks, and other tweaks to enhance your workflow.

<br><br>
## Objectives

I. Define useful Git aliases \
II. Explore Git hooks for automated tasks \
III. Adjust global `.gitignore` and other settings

<br><br>

## I. Git Aliases
- Edit your global `.gitconfig` or run commands like:
  ```bash
  git config --global alias.co checkout
  git config --global alias.st status
  git config --global alias.cm "commit -m"
  ```

Now you can use `git co`, `git st`, and `git cm "message"`.

<br><br>
## II. Git Hooks
Each repository contains a `.git/hooks` folder with sample hooks. For example, a **pre-commit** hook (`pre-commit`) can run tests or linters.

1. Make the hook file executable:
   ```bash
   chmod +x .git/hooks/pre-commit
   ```
2. Customize it as needed.

<br><br>

## III. Global .gitignore

Create a global `.gitignore` file for OS or editor-specific files:
```bash
git config --global core.excludesfile ~/.gitignore_global
```

Add patterns like `.DS_Store`, `Thumbs.db`, or `*.swp`.

<br><br>
## Summary

Custom configurations streamline repetitive tasks and improve consistency across projects, making Git even more powerful and personalized.

<br><br>
**Next:** Lab 11: In-Depth Merge Conflict Resolution


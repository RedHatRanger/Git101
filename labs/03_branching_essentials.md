# Lab 3: Branching Essentials

Branches let you develop features and fixes independently from the main codebase. In **Lab 3**, we’ll cover creating branches, switching between them, and merging simple changes.


## Objectives

  I. Create and switch between branches \
 II. Understand best practices for branch naming \
III. Merge simple changes back into the main branch \
 IV. Resolve basic merge conflicts

<br><br><br<br>

## I. Creating a Branch

1. View current branches:
   ```bash
   git branch
   ```

2. Create a new branch and switch to it:
```bash
git branch feature/login
git checkout feature/login
```
Alternatively:
```bash
git checkout -b feature/login
```

<br><br>

## II. Making Changes on a Branch
1. Add or edit files related to your new feature:
```bash
echo "Login feature code" > login.md
```

2. Stage and commit:
```bash
git add login.md
git commit -m "Implement basic login feature"
```

<br><br>

## III. Merging into Main (or Master)
1. Switch back to your main branch:
```bash
git checkout main
```

2. Merge the feature branch:
```bash
git merge feature/login
```

3. View your history to see the merge commit:
```bash
git log --oneline --graph
```

<br><br>

## IV. Handling Simple Conflicts
1. If you have conflicting changes, Git will show conflict markers in your files.
2. Open the file, decide which changes to keep (or combine them), remove the conflict markers, then:
```bash
git add <conflicted-file>
git commit
```

<br><br>

## Summary
Branching allows parallel development without disrupting the main codebase. In the next labs, we’ll dig into more advanced branching and merging strategies.

<br><br>

**Next:** Lab 4: Working with Remotes



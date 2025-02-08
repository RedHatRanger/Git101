# Lab 3: Branching Essentials

Branches let you develop features and fixes independently from the main codebase. In **Lab 3**, we’ll cover creating branches, switching between them, and merging simple changes.

---

## Objectives

I. Create and switch between branches \
II. Understand best practices for branch naming \
III. Merge simple changes back into the main branch \
IV. Resolve basic merge conflicts

---

## I. Creating a Branch

1. View current branches:
   ```bash
   git branch
   ```

2. Create a new branch and switch to it:
   ```bash
git checkout -b feature/login
```

   Alternatively:
   ```bash
git branch feature/login
git checkout feature/login
```

---

## 2. Making Changes on a Branch

Add or edit files related to your new feature:
```bash
echo "Login feature code" > login.md
```

Stage and commit:
```bash
git add login.md
git commit -m "Implement basic login feature"
```

---

## 3. Merging into Main (or Master)

Switch back to your main branch:
```bash
git checkout main
```

Merge the feature branch:
```bash
git merge feature/login
```

View your history to see the merge commit:
```bash
git log --oneline --graph
```

---

## IV. Handling Simple Conflicts

If you have conflicting changes, Git will show conflict markers in your files.

Open the file, decide which changes to keep (or combine them), remove the conflict markers, then:
```bash
git add <conflicted-file>
git commit
```

---

## 5. Summary

Branching allows parallel development without disrupting the main codebase. In the next labs, we’ll dig into more advanced branching and merging strategies.

---

**Next:** Lab IV: Working with Remotes



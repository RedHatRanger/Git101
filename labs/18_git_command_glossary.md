# Lab 18: Git Command Glossary

Below, we’ve separated Git commands into two categories:

- **Porcelain (High-Level) Commands** – Common, user-facing commands for everyday tasks.
- **Plumbing (Low-Level) Commands** – Advanced or internal commands. Often used under the hood or for specialized workflows.

> **Note**: Sometimes, whether a command is considered porcelain or plumbing can be debatable. We’ve classified them according to commonly accepted usage and official Git documentation references. You may see them labeled differently in various resources.

---

## Porcelain Commands (High-Level)

These are the commands you’ll typically use in your day-to-day workflows—branching, committing, merging, and managing basic repository operations.

| **Command**  | **Description**                                                                                                   | **Basic Usage**                                                             |
|--------------|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| **add**      | Stages changes (adds them to the index) for the next commit.                                                      | `git add <file>`<br>`git add .`<br>`git add -p`                             |
| **am**       | Applies patches from a mailbox (emails) to a Git repository.                                                       | `git am <mbox/patch>`                                                       |
| **bisect**   | Uses a binary search to find the commit that introduced a bug.                                                     | `git bisect start`<br>`git bisect bad <rev>`<br>`git bisect good <rev>`      |
| **branch**   | Lists, creates, or deletes branches.                                                                               | `git branch`<br>`git branch <branchName>`<br>`git branch -d <branchName>`    |
| **checkout** | Switches branches or restores files to a prior state from a commit.                                               | `git checkout <branch>`<br>`git checkout -- <file>`                         |
| **cherry-pick** | Applies changes from a specific commit (or commits) onto the current branch.                                    | `git cherry-pick <commit>`                                                 |
| **clean**    | Removes untracked files from the working directory.                                                                | `git clean -f`<br>`git clean -fd`<br>`git clean -fdx`                        |
| **clone**    | Creates a local copy of a remote repository.                                                                       | `git clone <repo-url>`<br>`git clone <repo-url> <dir>`                      |
| **commit**   | Records staged changes along with a message describing them.                                                       | `git commit -m "Message"`<br>`git commit -a -m "Message"`                 |
| **config**   | Reads and writes Git configuration options (e.g., user name, email).                                               | `git config --global user.name "Alice"`<br>`git config --list`             |
| **describe** | Generates a human-readable name for a commit (e.g., using the nearest tag).                                        | `git describe --tags`<br>`git describe --contains <commit>`                  |
| **diff**     | Shows changes between commits, branches, or the working tree and index.                                           | `git diff`<br>`git diff <branchA> <branchB>`                                |
| **fetch**    | Downloads commits, refs, and objects from another repository without merging.                                      | `git fetch <remote>`<br>`git fetch --all`                                   |
| **grep**     | Searches for lines matching a pattern in tracked files.                                                            | `git grep <pattern>`<br>`git grep -n <pattern>`                             |
| **gui**      | Launches Git’s built-in GUI tools (if installed).                                                                  | `git gui`                                                                   |
| **init**     | Creates a new Git repository or reinitializes an existing one.                                                     | `git init`<br>`git init --bare`                                             |
| **log**      | Shows the commit history, with various formatting and filtering options.                                           | `git log`<br>`git log --oneline --graph --decorate`                         |
| **merge**    | Joins two or more development histories, usually merging a branch into the current branch.                         | `git merge <branch>`<br>`git merge --no-ff <branch>`                        |
| **mv**       | Moves or renames a file, updating the index to reflect the change.                                                 | `git mv <old> <new>`                                                        |
| **pull**     | Fetches changes from a remote and merges them into the current branch.                                             | `git pull <remote> <branch>`                                                |
| **push**     | Updates remote refs using local refs, sending local commits to a remote repository.                                | `git push <remote> <branch>`<br>`git push --tags`                           |
| **rebase**   | Reapplies commits on top of another base tip, modifying commit history.                                            | `git rebase <branch>`<br>`git rebase -i <branch>`                           |
| **reset**    | Moves the current branch pointer and optionally modifies the index or working tree to match.                       | `git reset <commit>`<br>`git reset --soft <commit>`<br>`git reset --hard <commit>` |
| **restore**  | Restores working tree files or staged snapshot from a commit (newer porcelain command).                            | `git restore <file>`<br>`git restore --staged <file>`                       |
| **revert**   | Creates a new commit that undoes the changes of a specific earlier commit.                                         | `git revert <commit>`                                                      |
| **rm**       | Removes files from the working tree and the index.                                                                | `git rm <file>`<br>`git rm --cached <file>`                                 |
| **show**     | Displays information about a Git object (commit, tag, etc.).                                                      | `git show <commit>`<br>`git show HEAD~1`                                   |
| **stash**    | Temporarily shelves changes for later reapplication, leaving a clean working directory.                           | `git stash`<br>`git stash pop`                                              |
| **status**   | Shows the current state of the working tree and staging area.                                                     | `git status`<br>`git status -s`                                            |
| **switch**   | Switches to a specified branch or creates and switches to a new branch (newer command).                           | `git switch <branch>`<br>`git switch -c <new-branch>`                       |
| **tag**      | Creates, lists, or deletes tags and can verify GPG-signed tags.                                                    | `git tag <tagName>`<br>`git tag -a <tagName> -m "message"`                |

---

## Plumbing Commands (Low-Level)

These commands operate at a lower level, often used by scripts, more advanced users, or Git’s own internal processes. You may not need them in day-to-day work, but they’re powerful tools for specialized tasks.

| **Command**         | **Description**                                                                                                   | **Basic Usage**                                                             |
|---------------------|-------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|
| **archive**        | Creates an archive (e.g., .tar or .zip) of files from a named tree.                                                | `git archive --format=tar HEAD > source.tar`                                |
| **bundle**         | Moves objects and refs by archive (can bundle a Git repo into a single file).                                      | `git bundle create <file> <branch>`<br>`git bundle verify <file>`           |
| **cat-file**       | Examines a Git object’s contents (commits, trees, blobs, tags).                                                    | `git cat-file -p <object>`<br>`git cat-file -t <object>`                    |
| **check-attr**     | Displays gitattributes information (e.g., attributes set for particular paths).                                    | `git check-attr <attribute> -- <path>`                                      |
| **check-ignore**   | Displays patterns that match specified file paths (why files are ignored).                                          | `git check-ignore <file>`<br>`git check-ignore -v <file>`                   |
| **check-mailmap**  | Checks and applies mailmap file rules to canonicalize author and committer names and emails.                      | `git check-mailmap <email-or-name>`                                         |
| **check-ref-format** | Ensures a reference (branch, tag) name is well-formed.                                                          | `git check-ref-format <ref>`                                               |
| **checkout-index** | Copies files from the index to the working tree (low-level).                                                      | `git checkout-index --all`                                                  |
| **cherry**         | Lists commits in one branch that are not merged into another.                                                     | `git cherry <upstream> <head>`                                              |
| **citool**         | Launches a graphical (Tk) interface for committing changes.                                                       | `git citool`                                                                |
| **commit-tree**    | Creates a new commit object without updating refs (very low-level).                                               | `git commit-tree <tree> -p <parent> -m "Message"`                           |
| **count-objects**  | Counts unpacked objects in the .git directory.                                                                    | `git count-objects -v`                                                      |
| **credential**     | Manages credentials (username/password) for HTTP or other protocols.                                              | `git credential fill`<br>`git credential approve`                           |
| **credential-cache** | Helper for temporarily caching credentials in memory.                                                          | `git config credential.helper cache`                                        |
| **credential-store** | Helper for storing credentials on disk (plaintext).                                                            | `git config credential.helper store`                                        |
| **filter-branch**  | Rewrites branches by filtering commits (deprecated, use `git filter-repo`).                                      | `git filter-branch --tree-filter 'rm filename' HEAD`                        |
| **format-patch**   | Prepares patches suitable for email submission, each commit becomes a patch file.                                 | `git format-patch <since>`<br>`git format-patch -1 <commit>`                |
| **fsck**           | Verifies the integrity of Git objects (file system check).                                                       | `git fsck`<br>`git fsck --full`                                             |
| **gc**             | Cleans up unnecessary files and optimizes the repo (garbage collection).                                         | `git gc`<br>`git gc --prune=now --aggressive`                               |
| **get-tar-commit-id** | Reads a tar archive created by git archive and extracts the commit ID.                                         | `git get-tar-commit-id < archive.tar`                                       |
| **hash-object**    | Computes the object ID (SHA-1 or SHA-256) for a file.                                                            | `git hash-object <file>`<br>`git hash-object -w <file>`                     |
| **index-pack**     | Builds pack index files for existing packs.                                                                      | `git index-pack <pack-file>`                                               |
| **merge-base**     | Finds a common ancestor between two commits (useful for merges/rebases).                                         | `git merge-base <commit1> <commit2>`                                        |
| **merge-file**     | Performs a three-way merge of files outside Git’s typical merge workflow.                                         | `git merge-file <current-file> <base-file> <other-file>`                    |
| **merge-index**    | Low-level command that runs a merge for files in the index.                                                      | `git merge-index <merge-program> <file1> <file2>`                           |
| **notes**          | Adds, removes, or reads notes (annotations) attached to objects (commits, etc.).                                 | `git notes add <commit>`<br>`git notes show <commit>`                       |
| **pack-objects**   | Creates a pack file of objects for efficient transfer/storage.                                                   | `git pack-objects <pack-name>`                                             |
| **prune**          | Removes remote-tracking branches or other refs that no longer exist on the remote.                              | `git remote prune <remote>`<br>`git prune`                                  |
| **prune-packed**   | Removes extra objects that are already in pack files.                                                            | `git prune-packed`                                                          |
| **read-tree**      | Reads tree information into the index.                                                                           | `git read-tree <tree-ish>`                                                 |
| **reflog**         | Shows a history of changes to the tip of branches (all moves of `HEAD`).                                        | `git reflog`<br>`git reflog show <branch>`                                  |
| **remote**         | Manages a set of tracked repositories (remotes).                                                                | `git remote -v`<br>`git remote add origin <url>`                            |
| **replace**        | Creates temporary rewrites of Git objects (for experimentation).                                                | `git replace <object> <replacement>`                                       |
| **request-pull**   | Summarizes the changes between two commits to ask someone else to pull them.                                    | `git request-pull <start> <url> <end>`                                     |
| **rev-list**       | Lists commit objects in reverse chronological order.                                                            | `git rev-list <ref>`<br>`git rev-list --max-count=10 HEAD`                 |
| **rev-parse**      | Parses and resolves revision (branch/tag/commit) names.                                                         | `git rev-parse HEAD`<br>`git rev-parse --short <commit>`                    |
| **send-pack**      | Pushes to a remote repository (low-level counterpart to `git push`).                                            | `git send-pack <remote> <refspec>`                                         |
| **shortlog**       | Summarizes `git log` output by author or other criteria.                                                        | `git shortlog -n`<br>`git shortlog -s`                                      |
| **show-ref**       | Lists references in a local repository.                                                                         | `git show-ref`                                                              |
| **submodule**      | Manages submodules (repos embedded within another repo).                                                        | `git submodule add <repo-url>`<br>`git submodule update --init --recursive` |
| **subtree**        | Merges subtrees and splits a repository into subtrees (extension script).                                       | `git subtree add --prefix=<dir> <repo> <branch>`                            |
| **svn**            | Provides bidirectional flow between Subversion and Git.                                                         | `git svn clone <svn-repo>`<br>`git svn rebase`                              |
| **symbolic-ref**   | Reads or updates a symbolic reference (e.g., `HEAD`).                                                           | `git symbolic-ref HEAD refs/heads/<branch>`                                 |
| **unpack-file**    | Expands a packed archive file (created by git repacking).                                                       | `git unpack-file <file>`                                                   |
| **unpack-objects** | Unpacks objects from a pack file into .git/objects.                                                            | `git unpack-objects < pack-file.pack`                                       |
| **update-index**   | Modifies index entries, optionally writing changes to disk.                                                     | `git update-index --assume-unchanged <file>`                                |
| **update-ref**     | Updates a Git reference (branch, tag) safely.                                                                   | `git update-ref <ref> <commit>`                                            |
| **update-server-info** | Updates auxiliary info files for dumb transports.                                                          | `git update-server-info`                                                   |
| **upload-archive** | Transfers archive files from the remote repo to the local.                                                      | `git upload-archive --remote=<remote> <options>`                            |
| **upload-pack**    | Runs on the server side to send objects for fetching (underlying `git fetch`).                                  | `git upload-pack <dir>`                                                    |
| **var**            | Prints various Git logical variables (like `GIT_AUTHOR_IDENT`).                                                 | `git var <variable>`                                                       |
| **verify-commit**  | Checks the GPG signature of commits if signed.                                                                  | `git verify-commit <commit>`                                               |
| **verify-pack**    | Verifies the integrity of packed Git archive files.                                                             | `git verify-pack <pack-file>`                                              |
| **verify-tag**     | Checks the GPG signature of a tag if signed.                                                                    | `git verify-tag <tagName>`                                                |
| **worktree**       | Manages multiple working trees attached to the same repository.                                                | `git worktree add <path> <branch>`                                         |
| **write-tree**     | Creates a tree object from the current index (very low-level).                                                  | `git write-tree`                                                           |

---

## Using This Full List

1. **Porcelain vs. Plumbing**: We’ve made our best effort to classify them. Porcelain commands are typically used in everyday operations, while plumbing commands are lower-level and more specialized.
2. **Check Version Differences**: Commands like `restore` and `switch` are relatively new. Some commands may not exist or may be deprecated in certain Git versions.
3. **Explore Thoroughly**: Many commands have advanced flags or subcommands. Always refer to `git help <command>` or the [official Git docs](https://git-scm.com/docs) for details.

With these lists, you can quickly see which commands are most relevant for daily use versus more specialized scripting or repository maintenance tasks. Happy Git-ing 'Er Done!

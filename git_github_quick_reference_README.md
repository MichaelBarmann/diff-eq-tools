# Git & GitHub Quick Reference

## 0) What are Git and GitHub, and why do they matter?

**Git** is a version control system that keeps a history of your project as a sequence of snapshots called *commits*. It lets you see what changed, recover old versions, and organize your work as it evolves.

**GitHub** is a website that hosts Git repositories online. It provides backup, synchronization between machines, sharing, collaboration, and a convenient way to browse project history.

For PDE/ODE projects, Git provides a record of how solvers, notebooks, and utilities evolve over time.

---

# 1) Basic Git Definitions

| Term | Meaning |
|---------|---------|
| **Git** | A version control system that records the history of a project. |
| **GitHub** | A website that hosts Git repositories online. |
| **Repository (repo)** | A folder that Git is managing. |
| **Commit** | A saved snapshot of the repository at a particular time. |
| **Commit message** | A short description of what changed in a commit. |
| **Tracked file** | A file Git is monitoring for changes. |
| **Untracked file** | A file that exists but has not yet been added to Git. |
| **Working directory** | The actual files currently on your computer. |
| **Staging area** | The set of changes that will be included in the next commit. |
| **Branch** | An independent line of development (you currently use `main`). |
| **Remote** | An online copy of the repository (e.g. GitHub). |
| **origin** | The conventional name for the GitHub remote repository. |
| **Push** | Upload local commits to GitHub. |
| **Pull** | Download commits from GitHub. |
| **HEAD** | Your current location in the repository history. |
| **Diff** | A description of the differences between two versions of a file. |

---

# 2) Git Commands We've Learned

| Command | Purpose |
|----------|----------|
| `git init` | Create a Git repository in the current folder. |
| `git status` | Show what has changed and what is staged. |
| `git add file` | Stage a file for the next commit. |
| `git add .` | Stage all changed files. |
| `git commit -m "message"` | Create a new commit. |
| `git push` | Upload commits to GitHub. |
| `git log --oneline` | Show a concise commit history. |
| `git show --stat` | Show details about the most recent commit. |
| `git diff` | Show unstaged changes. |
| `git diff --cached` | Show staged changes. |
| `git --no-pager diff` | Show diffs without opening the pager. |
| `git mv old new` | Rename a file while preserving history. |
| `git ls-files` | List all tracked files. |
| `git config --global user.name "Name"` | Set your Git username. |
| `git config --global user.email "email"` | Set your Git email. |
| `git remote add origin URL` | Connect local repository to GitHub. |
| `git remote set-url origin URL` | Change the GitHub repository URL. |
| `git branch -M main` | Rename the current branch to `main`. |

---

# 3) Typical Workflow

## Creating a New File

```text
Create file
↓
git status
↓
git add file
↓
git commit -m "Add file"
↓
git push
```

## Modifying an Existing File

```text
Edit file
↓
git status
↓
git diff       (optional)
↓
git add file
↓
git diff --cached   (optional)
↓
git commit -m "Describe change"
↓
git push
```

## Renaming a File

```text
git mv old_name new_name
↓
git commit -m "Rename file"
↓
git push
```

---

# 4) Key Points to Remember

- Git stores snapshots, not every keystroke.
- Only commits are saved permanently.
- A commit represents the state of the entire repository.
- New files are not tracked automatically.
- Use `git add` and commit them once.
- Tracked files stay tracked.
- Git automatically notices future modifications.
- `git add` does not create a commit; it stages changes.
- Nothing is permanently saved until you commit.
- Nothing is uploaded to GitHub until you push.
- `git status` is your best friend.
- Write meaningful commit messages.
- Commit at stable checkpoints.
- A clean repository is a happy repository.

---

# 5) The Most Important Git Idea: A Commit is a Snapshot of the Entire Repository

A commit is not attached to a particular file. A commit is a snapshot of the entire repository at a particular moment in time.

Suppose the repository contains:

```text
Manifest.toml
ReadMe.md
notebooks/
    etd_euler.ipynb
    phi_functions.ipynb
```

## Commit A

```text
Manifest.toml          version 1
ReadMe.md             version 1
etd_euler.ipynb       version 1
phi_functions.ipynb   version 1
```

## Commit B

Only `etd_euler.ipynb` changes:

```text
Manifest.toml          version 1
ReadMe.md             version 1
etd_euler.ipynb       version 2
phi_functions.ipynb   version 1
```

## Commit C

Only `ReadMe.md` changes:

```text
Manifest.toml          version 1
ReadMe.md             version 2
etd_euler.ipynb       version 2
phi_functions.ipynb   version 1
```

Git stores a sequence of repository snapshots:

```text
Commit A
    ↓
Commit B
    ↓
Commit C
```

When you run:

```powershell
git status
```

Git compares:

```text
Current repository state
        versus
Most recent commit
```

and reports which files differ.

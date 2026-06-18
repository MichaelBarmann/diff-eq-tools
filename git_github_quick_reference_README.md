# Git & GitHub Quick Reference

## 0) What are Git and GitHub, and why do they matter?

**Git** is a version control system that keeps a history of your project as a sequence of snapshots called *commits*. It lets you see what changed, recover old versions, and organize your work as it evolves.

**GitHub** is a website that hosts Git repositories online. It provides backup, synchronization between machines, sharing, collaboration, and a convenient way to browse project history.

For PDE/ODE projects, Git provides a record of how solvers, notebooks, and utilities evolve over time. Instead of maintaining files such as

```text
etd_rk4_final.ipynb
etd_rk4_final_v2.ipynb
etd_rk4_final_v2_fixed.ipynb
```

you can keep a clean repository and let Git remember the history.

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

A healthy workflow for a personal research repository is:

```powershell
git status
git add .
git commit -m "Meaningful description"
git push
```

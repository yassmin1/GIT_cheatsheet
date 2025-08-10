## 📝 **GIT CHEAT SHEET** – Most Used Commands

---

### 📦 INIT & CLONE

| Command           | What It Does                                |
| ----------------- | ------------------------------------------- |
| `git init`        | Start a new Git repo in your current folder |
| `git clone <url>` | Copy a repo from GitHub to your computer    |

---

### 🧾 STAGING & COMMITS

| Command                   | What It Does                                         |
| ------------------------- | ---------------------------------------------------- |
| `git status`              | Show changes (what’s modified, staged, or untracked) |
| `git add .`               | Stage all changes for commit                         |
| `git add <file>`          | Stage a specific file                                |
| `git commit -m "message"` | Save staged changes with a message                   |

---

### 🔀 BRANCHING

| Command                  | What It Does                          |
| ------------------------ | ------------------------------------- |
| `git branch`             | List all branches                     |
| `git branch <name>`      | Create a new branch                   |
| `git switch <name>`      | Switch to a branch (modern)           |
| `git checkout <name>`    | Also switch to a branch (older style) |
| `git checkout -b <name>` | Create and switch to a new branch     |

---

### ⬆️ PUSH & ⬇️ PULL

| Command                    | What It Does                                   |
| -------------------------- | ---------------------------------------------- |
| `git remote -v`            | See where your repo is connected (like GitHub) |
| `git push origin <branch>` | Send your commits to GitHub                    |
| `git pull origin <branch>` | Get the latest changes from GitHub             |
| `git fetch`                | Get changes without merging yet                |
| `git merge <branch>`       | Merge another branch into the one you’re on    |

---

### 🔄 SYNC & FIX

| Command             | What It Does                                                |
| ------------------- | ----------------------------------------------------------- |
| `git pull --rebase` | Pull changes and reapply your work on top (cleaner history) |
| `git stash`         | Temporarily save your changes (like a shelf)                |
| `git stash pop`     | Bring back your stashed changes                             |
| `git reset <file>`  | Unstage a file you added                                    |
| `git reset --hard`  | ⚠️ Throw away all changes (careful!)                        |

---

### 🗑️ DELETE BRANCHES

| Command                             | What It Does                 |
| ----------------------------------- | ---------------------------- |
| `git branch -d <branch>`            | Delete a local branch (safe) |
| `git branch -D <branch>`            | Force delete a local branch  |
| `git push origin --delete <branch>` | Delete a branch from GitHub  |

---

### 🔍 LOG & HISTORY

| Command             | What It Does                             |
| ------------------- | ---------------------------------------- |
| `git log`           | Show commit history                      |
| `git log --oneline` | Short summary of commits                 |
| `git diff`          | Show changes not yet staged or committed |
| `git show <commit>` | Show what changed in a specific commit   |

---

### 🛠️ CONFIG

| Command                                            | What It Does                 |
| -------------------------------------------------- | ---------------------------- |
| `git config --global user.name "Your Name"`        | Set your name for all repos  |
| `git config --global user.email "you@example.com"` | Set your email for all repos |
| `git config -l`                                    | Show all your Git settings   |

---

### 🚨 BONUS: Undo & Fix

| Command                       | What It Does                                         |
| ----------------------------- | ---------------------------------------------------- |
| `git restore <file>`          | Undo changes to a file                               |
| `git restore --staged <file>` | Unstage a file                                       |
| `git commit --amend`          | Edit your last commit (message or content)           |
| `git reflog`                  | See all HEAD changes (can help recover lost commits) |

---

### 🎯 Pro Tip: GitHub Connection

```bash
git remote add origin https://github.com/user/repo.git
git push -u origin main
```


## ✅ **Step-by-Step: Create GitHub Repo from Command Line**

---

### 🧱 1. Create a New Local Repository

```bash

mkdir my-project
cd my-project
git init
echo "# My Project" > README.md
git add .
git commit -m "Initial commit"
```

---

### 🔐 2. Create a Repo on GitHub from CLI (with GitHub CLI)

First, make sure you have the [GitHub CLI](https://cli.github.com/) installed:

```bash
gh auth login  # Only once – to log into your GitHub account
```

Now create the repo:

```bash
gh repo create my-project --public --source=. --remote=origin --push
```

📌 Flags:

* `--public` or `--private`
* `--source=.` → use current folder
* `--remote=origin` → name the remote `origin`
* `--push` → push the code right after creating

---

### 🧠 Without GitHub CLI? Do It Manually:

1. Create a new repo on GitHub via web
2. Then add the remote like this:

```bash
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main  # or master
```


# Learn about git and gitHub

``` JavaScript
console.log("learn-git");

---

## 1️⃣ Git vs GitHub

* **Git** → Version Control System (VCS) that tracks code/files locally.
* **GitHub / GitLab / Bitbucket** → Cloud platforms to host Git repositories online, enabling collaboration & backup.

---

## 2️⃣ Repositories (Repo)

* A repo is a folder tracked by Git.
* **Types**:

  * **Local Repo** → on your computer
  * **Remote Repo** → hosted on GitHub/GitLab/Bitbucket

---

## 3️⃣ Git Config

Set user info & editor globally:

| Command                                                                                  | Explanation                   |
| ---------------------------------------------------------------------------------------- | ----------------------------- |
| git config --global user.name "Arjun Kumar"                                              | Set username globally         |
| git config --global user.email "[arjunadps662@gmail.com](mailto:arjunadps662@gmail.com)" | Set email globally            |
| git config --global core.editor "code --wait"                                            | Set VS Code as default editor |
| git config --list                                                                        | View all global settings      |

✅ **Best practice:** Always set username & email before starting a repo.

---

## 4️⃣ SSH Setup

Enables password-less authentication with GitHub/GitLab/Bitbucket.

**Steps:**

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

* Add the public key (`id_ed25519.pub`) to your GitHub/GitLab/Bitbucket account.

---

## 5️⃣ Special Files

* `.gitignore` → files/folders to ignore in Git
* `.env` → stores sensitive data (API keys, passwords)
* **Git Ignore Generator:** [toptal.com/developers/gitignore](https://www.toptal.com/developers/gitignore)

---

## 6️⃣ Basic Commands

| Command                            | Explanation                                      |
| ---------------------------------- | ------------------------------------------------ |
| pwd                                | Show current folder path                         |
| cd <path>                          | Move into a directory                            |
| cd ../                             | Move up one folder                               |
| ls                                 | List files/folders                               |
| ls -Force                          | Show hidden files (PowerShell)                   |
| mkdir gitone                       | Create folder                                    |
| touch file.txt / New-Item file.txt | Create file                                      |
| git --version                      | Check Git version                                |
| git init                           | Initialize new repo                              |
| git status                         | Show current state (modified, staged, untracked) |

---

## 7️⃣ Commit Workflow

Flow: **Working Directory → Staging Area → Local Repo**

```bash
git add <file>       # Stage changes
git add .            # Stage all changes
git commit -m "message"  # Commit changes
```

**Best practices:**

* Atomic commits → one logical change per commit
* Examples:

```bash
git commit -m "Fix login bug"
git commit -m "Add navbar component"
```

---

## 8️⃣ Viewing History

```bash
git log           # Detailed commit history
git log --oneline # Short form (hash + message)
```

---

## 9️⃣ Git Remote

```bash
git remote -v           # List remotes
git remote add origin git@github.com:user/repo.git
git remote show origin  # Show remote details
```

---

## 🔟 Push & Fetch

```bash
git push -u origin main       # Push commits to remote
git push origin feature       # Push feature branch
git fetch origin              # Get remote changes without merging
git merge origin/main         # Merge after fetch
```

---

## 1️⃣1️⃣ Branching

```bash
git branch           # List branches
git branch <name>    # Create branch
git checkout <name>  # Switch branch
git switch <name>    # Modern switch
git switch -c <name> # Create & switch
```

---

## 1️⃣2️⃣ Merging & Deleting Branches

```bash
git merge <branch>   # Merge into current branch
git branch -d <branch>  # Delete branch safely (if merged)
git branch -D <branch>  # Force delete
```

---

## 1️⃣3️⃣ Merge Conflicts

* Occur when Git cannot auto-merge.
* Git shows markers:

```text
<<<<<<< HEAD
footer added
=======
footer was added successfully
>>>>>>> branch-name
```

* Resolve manually → `git add <file>` → `git commit`

---

## 1️⃣4️⃣ Git Stash

```bash
git stash       # Save uncommitted changes temporarily
git stash pop   # Apply latest stash and remove it
git stash list  # View all stashes
git stash apply # Apply stash but keep it
```

---

## 1️⃣5️⃣ Git Restore

```bash
git restore <filename>  # Discard changes in a file
```

---

## 1️⃣6️⃣ Git Diff

```bash
git diff                # Changes not staged
git diff --staged       # Staged changes
git diff <hash1> <hash2>  # Compare two commits
```

---

## 1️⃣7️⃣ Git Commit Shortcuts

```bash
git commit -am "message"
```

* `-a` → stage all tracked files
* `-m` → commit message
  ⚠ Only works for **tracked files**.

---

## 1️⃣8️⃣ Git Rebase

```bash
git checkout feature-branch
git fetch origin
git rebase main
```

* Resolve conflicts → `git add <file>` → `git rebase --continue`
  ⚠ Avoid rebasing shared branches.

---

## 1️⃣9️⃣ GitHub Codespaces

* Cloud-based VS Code environment
* Useful for **quick development without local setup**

---

## 2️⃣0️⃣ Typical Git Workflow

```bash
mkdir project && cd project
git init
git add file.txt
git commit -m "Initial commit"
git switch -c feature
git add . && git commit -m "Add feature"
git checkout main && git merge feature
git push -u origin main
git branch -d feature
```

---

## ⚡ Best Practices

* Small, atomic commits
* Clear commit messages
* Use `.gitignore` for sensitive files
* Delete feature branches after merging

---

## 🌟 Open Source Contribution Roadmap

1. **Talk** → Engage with community or maintainers
2. **Open an Issue** → Identify a problem or feature
3. **Get Issue Assigned** → Make sure it’s officially assigned
4. **Work & Add Value** → Solve issue or improve project
5. **Make a PR & Iterate** → Submit changes & update if needed
6. **Have Patience** → PRs may take time to review
7. **Remember:** PR ≠ job guarantee

---

## 🔹 Steps to Contribute

1. **Choose an Issue/Feature** → Look for `good first issue`, `beginner`
2. **Fork the Repository** → Click Fork
3. **Clone Locally**

```bash
git clone https://github.com/your-username/repo-name.git
cd repo-name
```

4. **Create a Branch**

```bash
git checkout -b feature-branch-name
```

5. **Make Changes** → Edit code/docs, test locally
6. **Stage & Commit**

```bash
git add .
git commit -m "Brief, clear description of changes"
```

7. **Push Branch**

```bash
git push origin feature-branch-name
```

8. **Open Pull Request (PR)** → Add title & description
9. **Review & Update** → Address feedback, push updates
10. **Merge & Celebrate** → PR merged ✅

**Pro Tip:** Always sync your fork before new contributions:

```bash
git fetch upstream
git checkout main
git merge upstream/main
```



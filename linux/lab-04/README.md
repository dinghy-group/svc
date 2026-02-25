# Git & GitHub – DevOps Student Guide

---

## 1. Install Git

### Windows
1. Go to [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Download and run the installer (default options are fine)
3. Verify:
```bash
git --version
```

### Ubuntu / Debian
```bash
sudo apt update
sudo apt install git -y
git --version
```

---

## 2. Create a GitHub Account

1. Go to [https://github.com](https://github.com)
2. Click **Sign up**
3. Enter your email, password, and username
4. Verify your email address

---

## 3. Configure Git (First Time Only)

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

Verify:
```bash
git config --list
```

---

## 4. Create a Private Repository on GitHub

1. Log in to GitHub
2. Click **+** (top right) → **New repository**
3. Fill in:
   - **Repository name** – e.g. `my-project`
   - Select **Private**
   - **Do NOT** check "Initialize this repository with a README"
4. Click **Create repository**

> Leaving it empty is important — you will push your local code into it in the next step.

---

## 5. Authenticate GitHub from the CLI

GitHub no longer accepts your account password over HTTPS. You need a **Personal Access Token (PAT)**.

### Generate a PAT:
1. GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. Click **Generate new token**
3. Give it a name, set an expiration, and check the **repo** scope
4. Copy the token — you will not see it again

### Save credentials so you don't retype every time:
```bash
git config --global credential.helper store
```

When Git asks for your password during `git push`, paste the token instead of your GitHub password.

---

## 6. Push a New Local Project to GitHub

```bash
# Create your project folder and navigate into it
mkdir my-project && cd my-project

# Initialize Git
git init

# Create your first file
echo "# My Project" > README.md

# Stage and commit
git add .
git commit -m "first commit"

# Rename default branch to main
git branch -M main

# Link to your private GitHub repo
git remote add origin https://github.com/<your-username>/<repo-name>.git

# Push
git push -u origin main
```

---

## 7. Connect an Existing Local Project to GitHub

If you already have a local folder with code:

```bash
cd /path/to/your/project

git init
git add .
git commit -m "initial commit"

git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

---

## 8. Day-to-Day Workflow

After the initial setup, your daily flow is:

```bash
# Check what changed
git status

# Stage your changes
git add .

# Commit with a meaningful message
git commit -m "describe what you changed"

# Push to GitHub
git push
```

---

## Quick Reference

| Command | Description |
|---|---|
| `git init` | Initialize a local repo |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Save a snapshot |
| `git remote add origin <url>` | Link to remote repo |
| `git push -u origin main` | First push to GitHub |
| `git push` | Push after first time |
| `git pull` | Pull latest changes from GitHub |
| `git status` | Check current state |
| `git log --oneline` | View commit history |
| `git clone <url>` | Download a remote repo |

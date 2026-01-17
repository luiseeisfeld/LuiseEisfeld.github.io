# Git & GitHub Cheat Sheet for Beginners

This guide will walk you through pushing your changes to GitHub step by step.

## Quick Reference (TL;DR)

```bash
git status                    # See what files changed
git add .                     # Stage all changes
git commit -m "Your message"  # Save changes with a message
git push                      # Upload to GitHub
```

---

## Step-by-Step Guide

### Step 1: Check What Changed

First, see what files you've modified:

```bash
git status
```

This shows:
- **Modified files** (in red) - files you changed but haven't staged yet
- **Staged files** (in green) - files ready to be committed
- **Untracked files** - new files not yet in git

**What you'll see:**
- Modified: `_sass/_variables.scss`
- Modified: `_sass/_base.scss`
- Modified: `_sass/_page.scss`
- New file: `GIT_CHEATSHEET.md`

---

### Step 2: Stage Your Changes

"Staging" means telling git which files you want to include in your commit.

**Option A: Stage all changes at once**
```bash
git add .
```
The `.` means "all files in the current directory"

**Option B: Stage specific files**
```bash
git add _sass/_variables.scss
git add _sass/_base.scss
git add _sass/_page.scss
git add GIT_CHEATSHEET.md
```

**Verify what's staged:**
```bash
git status
```
Now the files should appear in green (staged).

---

### Step 3: Commit Your Changes

A "commit" is like saving a snapshot of your changes with a message describing what you did.

```bash
git commit -m "Fix heading font sizes and CSS syntax errors"
```

**Good commit messages:**
- ✅ `"Fix heading font sizes and CSS syntax errors"`
- ✅ `"Update teaching page formatting"`
- ❌ `"changes"` (too vague)
- ❌ `"fix stuff"` (not descriptive)

**What happened:**
- Your changes are now saved locally in your git history
- They're NOT on GitHub yet (that's the next step)

---

### Step 4: Push to GitHub

"Pushing" uploads your commits to GitHub.

```bash
git push
```

**If this is your first time or you're on a new branch:**
```bash
git push origin main
```
(Replace `main` with `master` if that's your default branch name)

**What happens:**
- Git uploads your commits to GitHub
- Your website will update (if using GitHub Pages)
- Others can see your changes

---

## Complete Example Workflow

Here's a complete example of pushing your current changes:

```bash
# 1. Check what changed
git status

# 2. Stage all changes
git add .

# 3. Commit with a descriptive message
git commit -m "Fix heading font sizes (h4/h5/h6 now larger than body text) and fix CSS syntax errors"

# 4. Push to GitHub
git push
```

---

## Common Situations & Solutions

### "Your branch is ahead of 'origin/main' by X commits"

This means you have local commits that aren't on GitHub yet. Just run:
```bash
git push
```

### "Please tell me who you are"

Git needs to know your name and email. Run:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
Then try committing again.

### "Updates were rejected because the remote contains work..."

Someone (or you from another computer) pushed changes to GitHub. You need to pull first:
```bash
git pull
```
This downloads and merges remote changes. Then push again:
```bash
git push
```

### "Nothing to commit, working tree clean"

This means all your changes are already committed. If you want to push them:
```bash
git push
```

### Undo a mistake before committing

**Unstage a file:**
```bash
git reset HEAD filename
```

**Discard changes to a file (⚠️ WARNING: This deletes your changes!):**
```bash
git checkout -- filename
```

---

## Useful Commands to Know

### View Your Commit History
```bash
git log
```
Press `q` to exit.

### See What Changed in a File
```bash
git diff filename
```

### See All Changes (staged and unstaged)
```bash
git diff
```

### Check Which Branch You're On
```bash
git branch
```

---

## Best Practices

1. **Commit often** - Small, frequent commits are better than huge ones
2. **Write clear messages** - Describe what and why, not just what
3. **Check status first** - Always run `git status` before committing
4. **Test before pushing** - Make sure your site works locally first
5. **Pull before push** - If working with others, pull first to avoid conflicts

---

## For Your Specific Changes

Since you fixed the heading font sizes, here's a good commit message:

```bash
git commit -m "Fix heading font sizes: h4/h5/h6 now larger than body text, and fix CSS syntax errors"
```

Or more detailed:

```bash
git commit -m "Fix heading font sizes and CSS syntax errors

- Increase h4/h5/h6 font size from 0.75em to 1.1em (now larger than body text at 0.9em)
- Fix CSS syntax: add missing 'em' units to margin properties
- Fixes issue where headings appeared smaller than regular text on teaching page"
```

---

## Need Help?

- **Git documentation:** https://git-scm.com/doc
- **GitHub Guides:** https://guides.github.com
- **Check your git version:** `git --version`
- **Get help on any command:** `git help <command>` (e.g., `git help push`)

---

## Quick Troubleshooting Checklist

Before pushing, make sure:
- ✅ You're in the right directory (your repo folder)
- ✅ You've saved all your file changes
- ✅ You've staged your changes (`git add`)
- ✅ You've committed your changes (`git commit`)
- ✅ You have internet connection
- ✅ You have permission to push (you're the owner or have write access)

---

**Happy coding! 🚀**

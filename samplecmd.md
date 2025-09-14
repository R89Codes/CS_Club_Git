# 📝 GitHub Workshop Command Sheet (Fork → Branch → PR)

This sheet shows the complete flow **from first change to opening a Pull Request**, plus a short breakdown and quick fixes.

---

## ✅ Prerequisites
- Git installed (Git Bash on Windows; Terminal on macOS/Linux)
- GitHub account (logged in in your browser)
- (Optional) GitHub CLI installed and authenticated once: `gh auth login`

---

## ⚡ One‑Shot Command Block (with GitHub CLI)
> Assumes you already **forked** the repo, **cloned your fork**, and are inside the repo folder.

```bash
# 1) create a branch
git checkout -b alice-goals

# 2) make your change
echo "I want to learn Web Development and AI." > goals_alice.txt

# 3) stage, commit, push
git status
git add goals_alice.txt
git commit -m "Add my learning goal"
git push origin alice-goals

# 4) open a Pull Request (from your branch to the club repo's main)
gh pr create --base main --head alice-goals   --title "Learning Goals – Alice"   --body "Adds my learning goal in goals_alice.txt"
```

**No GitHub CLI?** Do steps 1–3, then open your fork in the browser and click **Compare & pull request**.

---

## 🔍 Step‑by‑Step Breakdown

### 1) Create your branch (safe workspace)
```bash
git checkout -b yourname-goals
```
Why: Keep your changes isolated and easy to review.

### 2) Make your change
- Option A (new file):
  ```bash
  echo "I want to learn Web Development and AI." > goals_yourname.txt
  ```
- Option B (edit shared file): add one line in `learning_goals.md`:
  ```text
  - Your Name: I want to learn about Cybersecurity and Cloud Computing.
  ```

### 3) Stage the change (select what goes into the commit)
```bash
git status
git add goals_yourname.txt     # or: git add learning_goals.md
```

### 4) Commit with a clear message (save a snapshot)
```bash
git commit -m "Add my learning goal"
```

### 5) Push your branch to your fork on GitHub
```bash
git push origin yourname-goals
```

### 6) Open a Pull Request (PR)
- **Using GitHub CLI:**
  ```bash
  gh pr create --base main --head yourname-goals     --title "Learning Goals – Your Name"     --body "Adds my learning goal"
  ```
- **Using the Web UI:**
  1. Go to **your fork** on GitHub.
  2. Click **Compare & pull request**.
  3. Ensure **Base repository** is the club repo and **base branch** is `main`.
  4. Ensure **Compare** is your branch `yourname-goals`.
  5. Submit the PR.

### 7) Address review (if asked)
```bash
# make edits, then:
git add <file>
git commit -m "Address review feedback"
git push origin yourname-goals   # PR updates automatically
```

### 8) Merge (done by maintainer)
Once approved and merged, your change appears in the club’s `main` 🎉

---

## 🆘 Quick Troubleshooting

- **“Permission denied” or push rejected**  
  You’re pushing to the club repo, not your fork. Push to **origin** (your fork) and your **branch**:
  ```bash
  git push origin yourname-goals
  ```

- **PR points to the wrong place**  
  In the PR screen, set **base repo** to the club repo’s `main`, **compare** to your branch on your fork.

- **“Can’t be merged” (merge conflict)**  
  Update your branch from the club repo, fix conflicts, and push again:
  ```bash
  # one-time: add the club repo as upstream
  git remote add upstream https://github.com/<club-org-or-owner>/CS-Club-Git-Practice.git

  git fetch upstream
  git checkout yourname-goals
  git merge upstream/main    # or: git rebase upstream/main

  # fix conflicts in editor
  git add <fixed-files>
  git commit
  git push origin yourname-goals
  ```

- **“Nothing to commit”**  
  You forgot to change or stage something. Make an edit, then:
  ```bash
  git add <file>
  git commit -m "message"
  ```

---

## 🔄 (Optional) Keep your fork updated for future contributions
```bash
git remote add upstream https://github.com/<club-org-or-owner>/CS-Club-Git-Practice.git
git checkout main
git pull upstream main
git push origin main
git checkout -b yourname-next-change
```

Happy collaborating! 🚀

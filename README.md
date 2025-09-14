# 🚀 CS Club GitHub Practice

Welcome to the **GitHub Practice Repository** for our Computer Science Club! 🎉  
This activity teaches the real-world GitHub flow: **fork → clone → branch → add → commit → push → pull request → merge**.

---

## 🎯 Your Task
Add what you want to **learn or achieve** in this club (your learning goal).  
You can either (A) create your own small file or (B) add one line to `learning_goals.md`.

---

## ✅ Prerequisites
- A GitHub account (logged in)
- Git installed on your computer (Windows: Git Bash; macOS/Linux: Terminal)

---

## 🛠 Step-by-Step Instructions

### 1) Fork this repository (make your own copy)
- Click the **Fork** button at the top-right of this page.
- This creates **your own copy** of the repo under your GitHub account.

---

### 2) Clone *your fork* to your computer
- On **your forked repo page**, click the green **Code** button → copy the **HTTPS** URL.
- Open Git Bash/Terminal and run:
```bash
git clone https://github.com/<your-username>/CS-Club-Git-Practice.git
cd CS-Club-Git-Practice
```
> Replace `<your-username>` with your GitHub username.

---

### 3) Create your own branch (your safe workspace)
A **branch** is where you make changes without affecting others.
```bash
git checkout -b yourname-goals
```
Example:
```bash
git checkout -b alice-goals
```

---

### 4) Add your learning goal (pick ONE option)

**Option A — Create your own file**
```bash
echo "I want to learn about Web Development and AI." > goals_yourname.txt
```

**Option B — Add a line to the shared file**
- Open `learning_goals.md` in any editor and add a line like:
```
- Alice: I want to learn about Cybersecurity and Cloud Computing.
```

---

### 5) Stage your change (tell Git what to include)
```bash

git add goals_yourname.txt
# or
git add learning_goals.md
```

---

### 6) Commit your change (save a snapshot with a message)
```bash
git commit -m "Added my learning goal: [your goal here]"
```
Example:
```bash
git commit -m "Added my learning goal: Web Dev + AI"
```

---

### 7) Push your branch to **your fork** on GitHub
```bash
git push origin yourname-goals
```

---

### 8) Open a Pull Request (PR) to the main club repo
1. Go to **your fork** on GitHub.  
2. You’ll see a prompt to open a PR → click **Compare & pull request**.  
3. Check the targets carefully:
   - **Base repository:** `<club-org-or-owner>/CS-Club-Git-Practice`  
   - **Base branch:** `main`  
   - **Compare:** `yourname-goals` (your branch)  
4. Title suggestion: **Learning Goals – Your Name**  
5. Click **Create pull request**. 🎉

After a reviewer merges it, your contribution appears in the main repo.

---

## 📌 Example Contributions
- John Doe: I want to improve my Git skills and learn AI.
- Jane Smith: I want to build a project using APIs.


---

## 🆘 Quick Troubleshooting
- **Permission denied / auth errors** → Make sure you’re pushing to **your fork** (`origin`), not the club repo.  
- **Nothing to commit** → You forgot step 4 or step 5 (`git add .`).  
- **Wrong base/compare in PR** → Set **base** to the club repo’s `main`, **compare** to your branch on your fork.  
- **Merge conflicts** → Ask a mentor; we’ll resolve it together in session.

---

## 🙌 Code of Conduct
Be respectful, helpful, and keep your changes focused on the learning-goal activity.

---

## 📚 Files in this Repo
- `README.md` — this guide  
- `learning_goals.md` — shared list where you can add your line (Option B)

Happy collaborating! 🚀

# 1) create a branch
git checkout -b alice-goals

# 2) make your change
echo "I want to learn Web Development and AI." > goals_alice.txt

# 3) stage, commit, push
git status
git add goals_alice.txt
git commit -m "Add my learning goal"
git push origin alice-goals

# 4) open a Pull Request from your branch to the club repo's main
gh pr create --base main --head alice-goals \
  --title "Learning Goals – Alice" \
  --body "Adds my learning goal in goals_alice.txt"

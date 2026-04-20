# Drill - Undo things safely

**Time:** ~5 minutes

## Why this drill

You will mess something up. Knowing how to calmly undo the three most common mistakes is the difference between "oops" and "I need help, I broke everything."

## The drill

Three scenarios. Do each one.

### Scenario 1: Throw away an unstaged edit

```bash
echo "oops" >> README.md
git status                     # modified
git restore README.md          # throws the edit away
git status                     # clean
```

### Scenario 2: Unstage (keep the edit, just don't commit yet)

```bash
echo "wait" >> README.md
git add README.md
git status                     # staged
git restore --staged README.md # unstaged, edit preserved
git restore README.md          # throw edit away too
```

### Scenario 3: Fix a typo in the last commit message

```bash
echo "test" > scratch.txt
git add scratch.txt
git commit -m "fix: tpyo in message"     # oops

git commit --amend -m "fix: typo in message"
git log --oneline -1                      # message is fixed

# Clean up
rm scratch.txt
git add scratch.txt
git commit -m "chore: remove scratch file"
```

## Questions to answer in your daily log

- What's the difference between `git restore <file>` and `git restore --staged <file>`?
- What does `git commit --amend` do?
- Which of the three scenarios will you use most often?

## The one rule about undoing

**Never `git commit --amend` or `git reset --hard` on a commit you've already pushed and shared.** It rewrites history other people may have based their work on. On your own un-pushed commits, both are fine.

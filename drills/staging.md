# Drill - Stage, unstage, commit

**Time:** ~5 minutes
**Difficulty:** ★☆☆☆☆

## Why this drill

The staging area is the concept that trips up most new git users. This drill makes the three states - untracked, staged, committed - visible and tangible.

## The drill

Run these commands one at a time. Check `git status` between each step.

```bash
# 1. Make two file edits
echo "line A" > scratch-a.txt
echo "line B" > scratch-b.txt

# 2. Status: both are "untracked"
git status

# 3. Stage only A
git add scratch-a.txt

# 4. Status: A is "staged", B is "untracked"
git status

# 5. Unstage A
git restore --staged scratch-a.txt

# 6. Status: both untracked again

# 7. Stage and commit just A
git add scratch-a.txt
git commit -m "chore: add scratch file a"

# 8. Clean up
rm scratch-a.txt scratch-b.txt
```

## Questions to answer in your daily log

- In your own words, what is the "staging area" and why does it exist?
- What's the difference between `git add` and `git commit`?
- What does `git restore --staged <file>` do?

## Variations

- What happens if you run `git add .` instead of `git add scratch-a.txt`?
- How do you stage a *deletion* of a tracked file?
- What's the difference between `git restore <file>` and `git restore --staged <file>`?

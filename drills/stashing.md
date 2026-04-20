# Drill - Stashing work-in-progress

## Why this drill

You're mid-change on one thing when an urgent bug fix lands on main. Stash lets you set your current work aside and come back to it later.

## The drill

```bash
# 1. Make a change but don't commit
echo "half-done work" > wip.txt
git add wip.txt
git status                  # staged change

# 2. Stash it - working directory goes back to clean
git stash push -m "wip on feature x"
git status                  # clean

# 3. List your stashes
git stash list

# 4. See what's in the most recent stash
git stash show -p

# 5. Pop the stash back (apply + remove from stash list)
git stash pop
git status                  # wip.txt is staged again

# 6. Clean up
rm wip.txt
git restore --staged wip.txt
```

## Questions to answer in your daily log

- In your own words, what's a "stash"?
- What's the difference between `git stash pop` and `git stash apply`?
- When would you use a named stash (`stash push -m "message"`) vs an unnamed one?

## Variations

- Create two stashes and try `git stash pop stash@{1}` to pop a specific one.
- Try `git stash --include-untracked` when you have new (untracked) files - what's different?
- Read about `git stash branch <name>` - when would you use it?

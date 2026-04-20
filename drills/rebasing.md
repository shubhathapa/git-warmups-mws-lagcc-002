# Drill - Interactive rebase basics

**Time:** ~10 minutes

## Why this drill

Rebase lets you reshape history: squash commits, reorder them, edit messages, drop mistakes. It's the most powerful "clean up my work before sharing it" tool in Git. It's also the most dangerous tool if misused.

## The drill

```bash
# 1. Make three small commits on a throwaway branch
git checkout -b scratch/rebase-drill

echo "first" > file.txt
git add file.txt
git commit -m "add file"

echo "second" >> file.txt
git add file.txt
git commit -m "update file"

echo "third" >> file.txt
git add file.txt
git commit -m "updaet fiel"       # deliberate typo

git log --oneline -3               # three commits
```

```bash
# 2. Start an interactive rebase over the last three commits
git rebase -i HEAD~3
```

An editor opens with:

```
pick abc1234 add file
pick def5678 update file
pick ghi9012 updaet fiel
```

Change the third line from `pick` to `reword` (or `r`), save, close. Another editor opens with the typo'd message. Fix it. Save. Close.

```bash
# 3. Check the result
git log --oneline -3              # message fixed, but same three commits

# 4. Rebase again, this time squashing the middle two
git rebase -i HEAD~3
```

Change to:

```
pick abc1234 add file
squash def5678 update file
pick ghi9012 update file correctly
```

Save. Close. Edit the combined commit message when prompted. Save.

```bash
git log --oneline                 # two commits instead of three

# 5. Clean up
git checkout <your-username>
git branch -D scratch/rebase-drill
```

## Questions to answer in your daily log

- What did `reword` do vs what did `squash` do?
- Why might you rewrite history before pushing but not after?
- What does `pick` mean? What happens if you delete a `pick` line?

## The one rule about rebase

**Don't rebase commits you've already pushed and shared.** Rebasing rewrites history. If someone else has based their work on your old commits, rebasing strands them. On your own un-pushed commits, rebase freely.

## Variations

- Try `edit` instead of `reword` or `squash`. What does it let you do?
- Try `drop` on a commit. What happens?
- Try `git rebase -i --root` to rebase back to the very first commit.

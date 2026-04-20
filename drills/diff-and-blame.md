# Drill - Diff and blame

## Why this drill

`git diff` answers "what changed?" `git blame` answers "who changed this line and when?" You'll use both constantly in real work, especially when debugging.

## The drill

```bash
# 1. See what's different in your working directory vs the last commit
echo "test change" >> README.md
git diff
git diff --stat                # just file-level summary

# 2. Stage it, then see staged diff
git add README.md
git diff                       # empty now (nothing unstaged)
git diff --cached              # shows staged changes

# 3. Throw the change away
git restore --staged README.md
git restore README.md

# 4. Compare two commits
git log --oneline -5
git diff HEAD~2 HEAD           # what changed in the last 2 commits

# 5. See who last touched each line of a file
git blame README.md | head -20

# 6. See a commit's full patch
git log -p -1                  # last commit with full diff
git show <commit-sha>          # same for any commit
```

## Questions to answer in your daily log

- What's the difference between `git diff` and `git diff --cached`?
- What's the difference between `git diff HEAD` and `git diff HEAD~1`?
- When would you use `git blame`?

## Variations

- Try `git diff --word-diff` on a change to prose text. What's different from line-level diff?
- Use `git log -L :<function-name>:<file>` to see the history of a specific function.
- Read about `git bisect` - when you'd use it, and how it relates to blame.

# Drill - Working with remotes

**Time:** ~5 minutes
**Difficulty:** ★★☆☆☆

## Why this drill

`origin`, `upstream`, `fetch`, `pull`, `push` - these words get mixed up a lot. This drill makes the picture concrete.

## The drill

```bash
# 1. List your remotes
git remote -v

# 2. Fetch from origin (downloads changes but doesn't merge)
git fetch origin

# 3. See what's on the remote that isn't on your local branch
git log HEAD..origin/<your-username> --oneline

# 4. See what's on your local branch that isn't on the remote
git log origin/<your-username>..HEAD --oneline

# 5. Pull (fetch + merge in one step)
git pull

# 6. Check your upstream tracking
git branch -vv
```

## Questions to answer in your daily log

- What's the difference between `fetch` and `pull`?
- What's the difference between `origin` and `upstream` when a repo has both?
- What does `-u` do on `git push -u origin <branch>`?

## Variations

- Run `git remote add upstream <some-url>` then `git remote -v` again - what changed?
- Try `git push origin :some-dead-branch`. What does the colon-prefix do?
- What's `git push --force-with-lease` and why is it safer than `--force`?

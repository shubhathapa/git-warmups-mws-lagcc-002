# Drill - Branch, switch, delete

**Time:** ~5 minutes
**Difficulty:** ★★☆☆☆

## Why this drill

Branches are cheap in Git. New users treat them like they cost something; they don't. This drill makes creating and throwing away branches feel routine.

## The drill

```bash
# 1. Confirm where you are
git branch --show-current

# 2. Create and switch to a throwaway branch
git checkout -b scratch/drill-test

# 3. List all local branches
git branch

# 4. Switch back to your personal branch
git checkout <your-username>

# 5. Delete the throwaway
git branch -d scratch/drill-test

# 6. Confirm it's gone
git branch
```

## Questions to answer in your daily log

- What does `-b` do on `git checkout`? What happens without it?
- Why do branches exist? Answer in your own words.
- What's the difference between `git branch -d` and `git branch -D`?

## Variations

- Run `git branch -a`. What does `-a` show that `-b` alone doesn't?
- Create a branch with an unusual name like `fix/123-bug`. Does git allow slashes?
- What's a "detached HEAD"? Look it up and write one sentence.

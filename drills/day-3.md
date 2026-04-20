# Wednesday — Branch, switch, delete

**Time:** 5 minutes

## The drill

```bash
# 1. Confirm you're on your personal branch
git branch --show-current

# 2. Create a throwaway branch off your current one
git checkout -b scratch/wed-test

# 3. List all local branches — you should see your username branch AND scratch/wed-test
git branch

# 4. Switch back to your personal branch
git checkout <your-username>

# 5. Delete the throwaway branch
git branch -d scratch/wed-test

# 6. Confirm it's gone
git branch
```

## Your notes

Create `submissions/<your-username>/day-3.md`:

```markdown
# Wednesday warmup

## What `git checkout -b <name>` does
<1 sentence — what's different from `git checkout <name>` without the -b?>

## Why branches exist
<2 sentences in your own words — what problem do they solve?>

## Difference between `git branch -d` and `git branch -D`
<1 sentence — lowercase vs capital>
```

## Commit

```bash
git add submissions/<your-username>/day-3.md
git commit -m "docs(warmup-day-3): wednesday branching notes"
git push
```

## Bonus

- Run `git branch -a`. What does the `-a` flag show that `-b` doesn't?
- What's a "detached HEAD" state? (Google it, one sentence answer in your notes.)

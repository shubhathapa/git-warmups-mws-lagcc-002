# Monday — Reading `git status` and `git log`

**Time:** 5 minutes

## The drill

In your cloned copy of this repo, run each command below and **write down what you see.** Don't skim — read the output.

```bash
git status
git log --oneline
git log --oneline -5
git log --graph --oneline --all
```

## Your notes

Create `submissions/<your-username>/day-1.md` with:

```markdown
# Monday warmup

## What `git status` showed me
<3–4 sentences describing the sections you saw>

## What `git log --oneline` showed me
<1 sentence — what format is each line in?>

## What `git log --graph` added
<1 sentence — what's the graph drawing?>
```

## Commit

```bash
git add submissions/<your-username>/day-1.md
git commit -m "docs(warmup-day-1): monday reading status and log"
git push
```

## Bonus (optional, no extra credit)

- Run `git log --author="<your-name>"` — does it return anything?
- Run `git log --since="yesterday"` — what does it return when you haven't committed yet today?

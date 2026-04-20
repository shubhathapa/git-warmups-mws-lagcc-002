# Tuesday — Stage, unstage, commit

**Time:** 5 minutes

## The drill

In this repo, do the following in order. Don't batch the commands — run them one at a time and check `git status` between steps.

```bash
# 1. Make two file edits
echo "line A" > scratch-a.txt
echo "line B" > scratch-b.txt

# 2. Check status — both files should be "untracked"
git status

# 3. Stage only scratch-a.txt
git add scratch-a.txt

# 4. Status again — A is "staged", B is "untracked"
git status

# 5. Unstage A
git restore --staged scratch-a.txt

# 6. Status — both are "untracked" again

# 7. Now stage and commit just scratch-a.txt
git add scratch-a.txt
git commit -m "docs(warmup-day-2): add scratch file a"

# 8. Clean up — delete both scratch files and the commit doesn't matter,
#    they're ignored by .gitignore below
rm scratch-a.txt scratch-b.txt
```

## Your notes

Create `submissions/<your-username>/day-2.md`:

```markdown
# Tuesday warmup

## What "staging" means in my own words
<2 sentences>

## The difference between `git add` and `git commit`
<1 sentence>

## What `git restore --staged` does
<1 sentence>
```

## Commit your notes (in addition to the commit you made during the drill)

```bash
git add submissions/<your-username>/day-2.md
git commit -m "docs(warmup-day-2): tuesday staging notes"
git push
```

## Bonus

- What happens if you run `git add .` instead of `git add scratch-a.txt` in step 3?
- How do you stage a deletion? (Hint: `git rm` is one way, but `git add` also picks up deletions.)

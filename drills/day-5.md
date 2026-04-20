# Friday — Undo things safely

**Time:** 5 minutes

## The drill

Three common "oh no" moments and how to unwind each one.

### Scenario 1: "I edited a file and want to throw away my changes"

```bash
echo "oops" >> README.md        # pretend you made a bad edit
git status                      # README.md is now "modified"
git restore README.md           # throws away the change
git status                      # clean
```

### Scenario 2: "I staged a file and want to unstage it (keep the changes, just don't commit yet)"

```bash
echo "wait" >> README.md
git add README.md
git status                      # README.md is "staged"
git restore --staged README.md  # unstages but keeps the edit
git restore README.md           # now throw away the edit too
```

### Scenario 3: "I made a commit with a typo in the message"

```bash
echo "test" > scratch.txt
git add scratch.txt
git commit -m "fix: tpyo in message"   # oops

# Fix the last commit's message
git commit --amend -m "fix: typo in message"

# Clean up
git log --oneline -1            # confirm the message changed
rm scratch.txt                  # tidy
git add scratch.txt
git commit -m "chore: remove scratch file"
```

## Your notes

Create `submissions/<your-username>/day-5.md`:

```markdown
# Friday warmup

## `git restore <file>` vs `git restore --staged <file>`
<1 sentence each>

## What `git commit --amend` does
<1 sentence>

## One "undo" command I know I'll use a lot
<1 sentence — which of the three scenarios comes up the most in my work?>
```

## Commit

```bash
git add submissions/<your-username>/day-5.md
git commit -m "docs(warmup-day-5): friday undo notes"
git push
```

## The one rule about undoing

**Never `git commit --amend` or `git reset --hard` on a commit you've already pushed and shared with others.** It rewrites history that other people may have based their work on. On your own un-pushed commits, both are fine.

## Week 1 complete 🎉

Check your branch with `git log --oneline`. You should have at least 5 commits this week (one per day) plus the extra commits from Thursday's drill. That's a week of practice baked into history you can point to.

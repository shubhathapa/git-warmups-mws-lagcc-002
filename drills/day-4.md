# Thursday — Deliberately cause a merge conflict, then resolve it

**Time:** 5–10 minutes

## The drill

This is the longest warmup of the week. Do it slowly.

```bash
# Start on your personal branch
git checkout <your-username>

# 1. Create a file with one line
echo "hello from main" > conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore(warmup-day-4): add conflict demo file"

# 2. Make a branch that changes the file one way
git checkout -b scratch/conflict-branch-a
echo "hello from branch A" > conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: change demo text from branch A"

# 3. Go back and make a DIFFERENT change on the main branch
git checkout <your-username>
echo "hello from branch main" > conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: change demo text from main"

# 4. Try to merge — this WILL fail with a conflict
git merge scratch/conflict-branch-a
```

You should see an error like:

```
CONFLICT (content): Merge conflict in conflict-demo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

This is not a bug. This is git telling you "two branches changed the same line, I don't know which one you want."

## Resolve it

```bash
# Open the file in your editor
cat conflict-demo.txt
```

You'll see something like:

```
<<<<<<< HEAD
hello from branch main
=======
hello from branch A
>>>>>>> scratch/conflict-branch-a
```

Edit the file by hand to pick what you actually want — usually a combination, but for this drill just keep one line and delete the `<<<<<<<`, `=======`, and `>>>>>>>` markers.

```bash
# Final content should just be:
# hello from branch main (or branch A — your call)

git add conflict-demo.txt
git commit -m "fix(warmup-day-4): resolve merge conflict between main and branch-a"

# Clean up
git branch -D scratch/conflict-branch-a
rm conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: remove conflict demo file"
```

## Your notes

Create `submissions/<your-username>/day-4.md`:

```markdown
# Thursday warmup

## What caused the conflict in my own words
<2 sentences>

## What the conflict markers (<<<, ===, >>>) mean
<1 sentence>

## How I decided what to keep
<1 sentence>

## Was this scary or fine?
<honest 1-sentence answer>
```

## Commit

```bash
git add submissions/<your-username>/day-4.md
git commit -m "docs(warmup-day-4): thursday conflict notes"
git push
```

## Why Thursday is a big deal

Merge conflicts are the single most common reason new developers freeze. If you can resolve one calmly, you've cleared the biggest mental block in the whole curriculum.

# Drill - Cause and resolve a merge conflict

## Why this drill

Merge conflicts freeze more new developers than any other Git situation. Deliberately causing one (so you can resolve it) is the fastest way to kill that fear.

## The drill

```bash
# Start on your personal branch
git checkout <your-username>

# 1. Create a file
echo "hello from main" > conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: add conflict demo file"

# 2. Branch off and change the file one way
git checkout -b scratch/conflict-branch
echo "hello from branch" > conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: change demo text on branch"

# 3. Back to your branch, change the SAME file differently
git checkout <your-username>
echo "hello from home" > conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: change demo text on home branch"

# 4. Try to merge (this WILL conflict)
git merge scratch/conflict-branch
```

You'll see:

```
CONFLICT (content): Merge conflict in conflict-demo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

This is not a bug. Git is telling you "two branches changed the same line. I don't know which one you want."

## Resolving

```bash
cat conflict-demo.txt
```

You'll see conflict markers:

```
<<<<<<< HEAD
hello from home
=======
hello from branch
>>>>>>> scratch/conflict-branch
```

Edit the file. Keep one line (or combine them). Delete the `<<<<<<<`, `=======`, and `>>>>>>>` markers. Save.

```bash
git add conflict-demo.txt
git commit -m "fix: resolve merge conflict on conflict-demo.txt"

# Clean up
git branch -D scratch/conflict-branch
rm conflict-demo.txt
git add conflict-demo.txt
git commit -m "chore: remove conflict demo file"
```

## Questions to answer in your daily log

- What caused the conflict, in your own words?
- What do the `<<<`, `===`, `>>>` markers mean?
- How did you decide what to keep?
- Was this scary or fine? Honest answer.

## The rule about merge conflicts

They are normal. Professional developers resolve them weekly. The only thing that makes them scary is thinking they shouldn't happen.

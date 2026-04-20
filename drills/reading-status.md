# Drill - Reading `git status` and `git log`

## Why this drill

Half of all "my git is broken" moments are solved by actually reading the output of `git status`. This drill builds the habit of reading, not skimming.

## The drill

Run each command and read the output carefully. Don't skip to the next command until you understand what the last one told you.

```bash
git status
git log --oneline
git log --oneline -5
git log --graph --oneline --all
git diff
```

## Questions to answer in your daily log

- What are the sections of `git status` output? (modified, staged, untracked - what's each?)
- What format does each line of `git log --oneline` use?
- What's the graph in `--graph` actually drawing?
- What does `git diff` show when there are no changes? What about when there are unstaged changes?

## Variations (for when you come back to this drill)

- Try `git log --author="<your-name>"` - does it return anything on your branch?
- Try `git log --since="yesterday"` - what does it return?
- Try `git log -p -1` - what's `-p` adding?

# Drill - Tags and releases

## Why this drill

Tags mark specific commits as important, usually for releases (`v1.0.0`, `v2.3.1`). They're pointers that never move, unlike branches. Every real codebase uses them.

## The drill

```bash
# 1. List existing tags
git tag

# 2. Create a lightweight tag on the current commit
git tag v0.1.0

# 3. Create an annotated tag (with a message and author info)
git tag -a v0.2.0 -m "second milestone"

# 4. See the difference
git show v0.1.0 | head
git show v0.2.0 | head

# 5. List tags matching a pattern
git tag -l "v0.*"

# 6. Delete a local tag
git tag -d v0.1.0

# 7. Push a specific tag to the remote
git push origin v0.2.0

# 8. Delete a remote tag (when you no longer need it)
git push origin --delete v0.2.0
git tag -d v0.2.0
```

## Questions to answer in your daily log

- What's the difference between a lightweight tag and an annotated tag?
- Why might you use tags instead of branches for releases?
- How do you push all your local tags at once? (Hint: `git push --tags`.)

## Variations

- Tag a commit that isn't HEAD using `git tag v0.0.1 <commit-sha>`.
- Check out a tag: `git checkout v0.2.0`. What does git say about detached HEAD?
- Semantic versioning: read [semver.org](https://semver.org) and write one sentence on what `MAJOR.MINOR.PATCH` means.

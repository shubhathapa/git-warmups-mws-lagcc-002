---
languages: git, bash
tags: warmup, daily-practice, morning-drill, ongoing
resources: 2
---

# Daily Git Warmups

![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white&style=for-the-badge)
![Daily](https://img.shields.io/badge/cadence-daily-blue?style=for-the-badge)
![Duration](https://img.shields.io/badge/5_min%2Fday-green?style=for-the-badge)

## Background

Five minutes. Every morning. Before you open your editor.

These are the equivalent of stretching before exercise - small, repeated movements that keep your Git reflexes sharp. This is not a one-week assignment that ends after Friday. **You do one warmup every day** for the length of the program. Some days you'll pick a new drill; some days you'll redo one you've done before because it still feels slow.

Companion handbook page: [Module 1 - Program Setup, Git & GitHub](https://lgcc.github.io/modules/01-setup).

## Objectives

Across the weeks and months you spend on this, you should be able to, without looking up commands:

- Read `git status` and `git log` output and know what each section means
- Stage and unstage files, commit with clear messages
- Create, switch, and delete branches
- Diagnose and resolve a merge conflict calmly
- Undo common mistakes (bad edits, premature stages, typo'd messages)
- Work with remotes: fetch, pull, push, set upstream
- Stash work-in-progress, rebase safely, tag releases

## How this works

### One-time setup

```bash
git clone git@github.com:ttpr-lgcc/git-warmups-lagcc-002.git
cd git-warmups-lagcc-002
git checkout -b <your-username>
git push -u origin <your-username>
```

You work on **your personal branch** indefinitely. Your branch becomes a dated log of every warmup you've done - a history the instructor can scroll back through.

### Every morning

1. **Pick a drill** from [`drills/`](./drills/). You can pick any one. Beginner? Start with `reading-status.md`. Already comfortable there? Move to `branching.md`. Already automatic with branching? Try `rebasing.md`. You choose.
2. **Do the drill** in your terminal. Most take 3-5 minutes of actual commands.
3. **Log what you did** in a new file named after today's date: `submissions/<your-username>/YYYY-MM-DD.md`.
4. **Commit** with a message that names the drill you did:
   ```bash
   git add submissions/<your-username>/YYYY-MM-DD.md
   git commit -m "docs(warmup): <drill-name> - <one-line takeaway>"
   git push
   ```

That's it. One new commit on your branch per day.

### What goes in the daily log file

```markdown
# 2026-04-20 - <drill-name>

## Drill I did
<which drill from drills/ - e.g., staging>

## What I ran
<the commands, optional - a few key ones is enough>

## What I learned (or re-learned)
<1-3 sentences>

## What still feels slow
<1 sentence>
```

## The drill library

You rotate through these. Redoing one you've already done is not cheating - it's the entire point. The drills that feel hardest are the ones you should repeat most.

| Drill | What it teaches | Difficulty |
|---|---|---|
| [reading-status.md](./drills/reading-status.md) | Read `git status`, `git log`, `git diff` output | ★☆☆☆☆ |
| [staging.md](./drills/staging.md) | `add`, `restore --staged`, `commit` | ★☆☆☆☆ |
| [branching.md](./drills/branching.md) | `branch`, `checkout -b`, `branch -d` | ★★☆☆☆ |
| [conflicts.md](./drills/conflicts.md) | Deliberately cause a merge conflict, resolve it | ★★★☆☆ |
| [undoing.md](./drills/undoing.md) | `restore`, `commit --amend`, when to use which | ★★☆☆☆ |
| [remotes.md](./drills/remotes.md) | `fetch`, `pull`, `push`, upstream tracking | ★★☆☆☆ |
| [stashing.md](./drills/stashing.md) | `stash push`, `stash pop`, `stash list` | ★★☆☆☆ |
| [rebasing.md](./drills/rebasing.md) | Interactive rebase basics (squash, reorder) | ★★★★☆ |
| [tagging.md](./drills/tagging.md) | Lightweight vs annotated tags, pushing tags | ★★☆☆☆ |
| [diff-and-blame.md](./drills/diff-and-blame.md) | `diff`, `blame`, reading `log -p` | ★★☆☆☆ |

## Rules

- **One commit per calendar day.** Multiple commits in a day are fine; at least one must happen.
- **Keep the chain unbroken.** If you miss a day, log it honestly - "2026-04-20 - missed, here's why" - and move on. Don't backfill fake entries.
- **Same branch forever.** You're building a long-running history, not a PR per drill.
- **Redo drills.** If `conflicts.md` freaks you out on Monday, do it again Thursday. That's how you kill the fear.

## Checklist (check in monthly, not weekly)

- [ ] My branch has at least one commit per weekday for the last month
- [ ] I've done each drill at least twice
- [ ] There's at least one drill that used to feel hard and now doesn't
- [ ] I can run `status → branch → add → commit → push` without looking up commands

## Resources

- [Pro Git Book](https://git-scm.com/book/en/v2) - chapters 2 and 3 back every drill here
- [Oh Shit, Git!?!](https://ohshitgit.com/) - what to do when things go sideways
- [Git Cheat Sheet (GitHub)](https://training.github.com/downloads/github-git-cheat-sheet.pdf) - one page, print it, pin it

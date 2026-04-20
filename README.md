---
languages: git, bash
tags: warmup, morning-drill, daily-practice
resources: 2
---

# Morning Git Warmups — Week 1

![Stretching before the workout](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6e/Terminal_icon.svg/240px-Terminal_icon.svg.png)

## Background

Five 5-minute drills, one per morning, Monday through Friday of week 1. Do them before you open your editor. The goal is the same as stretching before exercise: warm up the muscles you're about to use.

Companion handbook page: [Module 1 — Program Setup, Git & GitHub](https://lgcc.github.io/modules/01-setup).

## Objectives

By Friday you should be able to, without looking up commands:

- Read `git status` output and know what each section means
- Stage and unstage files
- Commit with a clear message
- Create, switch, and delete branches
- Diagnose a common failure (rejected push, merge conflict, detached HEAD)

## How to use this repo

Once at the start of the week:

```bash
git clone git@github.com:ttpr-lgcc/git-warmups-lagcc-002.git
cd git-warmups-lagcc-002
git checkout -b <your-username>
git push -u origin <your-username>
```

All five days' submissions land on **your branch** — one commit per day. Same model as the drill: no pull requests, no forking, just push to your branch and the instructor reviews from there.

Each morning:

1. Read the day's drill in [`drills/`](./drills/).
2. Do the drill in your terminal. Most drills have you run 3–5 commands.
3. Record what you did in `submissions/<your-username>/day-<N>.md`.
4. Commit with `docs(warmup-day-<N>): <one-line summary>` and push.

## The week

| Day | Drill | Key commands |
|---|---|---|
| [Monday](./drills/day-1.md) | Reading `git status` and `git log` | `status`, `log --oneline` |
| [Tuesday](./drills/day-2.md) | Stage, unstage, commit | `add`, `restore --staged`, `commit` |
| [Wednesday](./drills/day-3.md) | Branch, switch, delete | `branch`, `checkout`, `branch -d` |
| [Thursday](./drills/day-4.md) | Simulate a merge conflict and resolve it | `merge`, manual edit |
| [Friday](./drills/day-5.md) | Undo things safely | `restore`, `reset`, `revert` |

## Rules

- **Same branch all week.** You're building a 5-commit history on your `<your-username>` branch.
- **One commit per day.** Multiple commits in a day are fine, but at least one must be dated that day.
- **Don't delete your notes.** Even a short "I didn't understand this one" is a real answer.

## Checklist

- [ ] Branch `<my-username>` on this repo has 5 commits, one per weekday
- [ ] `submissions/<my-username>/day-1.md` through `day-5.md` all exist
- [ ] Each day's file records what I ran and what happened

## Resources

- [Pro Git Book](https://git-scm.com/book/en/v2) — chapters 2–3 are the full reference
- [Oh Shit, Git!?!](https://ohshitgit.com/) — what to do when things go sideways

# AGENTS.md

Single markdown file (`abhiroop_faang_prep_plan.md`) — DSA + System Design interview prep tracker.
No code, no build, no tests, no CI. All work is updating the plan file.

## Commands (rtk prefix always)

```
rtk git status    rtk git diff     rtk git log
rtk read <file>   rtk grep <pat>   rtk ls <path>
rtk git add . && rtk git commit -m "msg"
```

## Workflow

- **Auto-commit enabled** — PostToolUse hook commits + pushes plan edits. Never manually commit.
- After each problem solve: update Progress Tracker (newest row first), Stats Summary, and Currently Assigned section.
- Merge same-day problems into one row with timestamped entries.
- Only trust what's logged in the Progress Tracker. If user mentions unlogged progress, ask for confirmation.

## Communication

- **Weekdays:** report quick-stats (time taken, approach, issues/hints).
- **Weekends:** full interview-style walkthrough.
- User logs sessions as real-time timestamped traces (e.g. "6:31: trying X"). Read as diagnostic signal.
- Language: Java. Platform: LeetCode. Always include clickable LeetCode link when assigning a problem.
- **Never offer a menu** — just assign the next problem. User opts in for more.

## Key Conventions

- Progress Tracker: newest rows at top.
- Stats Summary: update periodically (not every session).
- Currently Assigned: update with next problem after each solve.
- Confidence: 1-5 scale, include with each logged problem.
- Recurring gaps to watch: Java collection API mixups (poll/peek, contains/isPresent), "adjacency list" vs "adjacency matrix" terminology.

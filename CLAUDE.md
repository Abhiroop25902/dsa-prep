# AGENTS.md

This repo is a personal DSA + system design interview prep tracker. It contains a single file:

- `abhiroop_faang_prep_plan.md` — the living plan (roadmap, progress log, checklists, behavioral stories)

No build system, tests, lint, or CI. This is a markdown-only repo — the only meaningful action is updating the plan file.

## Agent instructions

The plan file itself has session instructions for AI assistants at the top. **Read and follow those.** Key rules in brief:

- **Don't invent progress.** Only trust logged rows in the Progress Tracker. If he mentions something that isn't logged, ask him to confirm/add it.
- **Default language is Java.** All code discussion in Java unless stated otherwise.
- **When he reports a session**, update the Progress Tracker row for that date (merge multiple problems from the same day into one row), tick checklist items, and update Stats Summary.
- **Time budget is 1–2 hrs/day** with a full-time job. Keep suggestions sized to that.
- **"Day" means calendar date**, not problem count. Multiple problems on the same date go in a single row with timestamped entries in the Notes column.
- **The doc is a memory aid, not a contract.** If what he tells you now conflicts with what's written in the plan, trust him and update the doc accordingly.
- After updating, suggest he copy the updated document back into his notes so state isn't lost between chats.

## Progressive load

Volume per day should increase gradually based on what's sustainable — don't jump to match a single strong day. But: if a problem finishes well under time (e.g. an Easy in <10 min), a follow-up in the same sitting is fine without waiting for the next session. Hard problems will naturally take longer; that's expected and not a reason to pile on more.

## Communication format

- **Weekdays:** quick-stats only (time taken, approach landed on, any issues/hints needed). No full walkthrough. Keeps sessions inside the 1-hr budget.
- **Once a week (weekend):** full interview-style walkthrough — talk through approach out loud, get pushed on trade-offs.
- He writes running timestamped logs *as it happens* (e.g. "6:31: trying X", "6:46: found bug Y") — read these as a real-time trace, not a polished report.
- **Confidence rating:** gauge it yourself from the solve — don't ask him. Factors: time vs target, bug count, whether approach was immediate or needed hints, code quality, difficulty level. State it when logging the session.

## Git workflow

After every plan update (progress logged, checklist ticked, stats synced), **commit and push automatically** — don't wait for the user to ask. Use a concise commit message summarizing what was solved/updated (e.g. "Day 2026-07-11: LC 424/20/704 solved, Sliding Window+Stack+Binary Search confirmed").

## Updating the file

- Append new Progress Tracker rows at the top of the table (newest first).
- If multiple problems are solved on the same date, merge them into one row with the date. List each problem in the Problem/Activity column and put timestamps + details in Notes.
- Keep the Stats Summary in sync when progress is logged.
- Don't reformat or restructure existing sections without being asked.


<!-- headroom:rtk-instructions -->
# RTK (Rust Token Killer) - Token-Optimized Commands

When running shell commands, **always prefix with `rtk`**. This reduces context
usage by 60-90% with zero behavior change. If rtk has no filter for a command,
it passes through unchanged — so it is always safe to use.

## Key Commands
```bash
# Git (59-80% savings)
rtk git status          rtk git diff            rtk git log

# Files & Search (60-75% savings)
rtk ls <path>           rtk read <file>         rtk grep <pattern>
rtk find <pattern>      rtk diff <file>

# Test (90-99% savings) — shows failures only
rtk pytest tests/       rtk cargo test          rtk test <cmd>

# Build & Lint (80-90% savings) — shows errors only
rtk tsc                 rtk lint                rtk cargo build
rtk prettier --check    rtk mypy                rtk ruff check

# Analysis (70-90% savings)
rtk err <cmd>           rtk log <file>          rtk json <file>
rtk summary <cmd>       rtk deps                rtk env

# GitHub (26-87% savings)
rtk gh pr view <n>      rtk gh run list         rtk gh issue list

# Infrastructure (85% savings)
rtk docker ps           rtk kubectl get         rtk docker logs <c>

# Package managers (70-90% savings)
rtk pip list            rtk pnpm install        rtk npm run <script>
```

## Rules
- In command chains, prefix each segment: `rtk git add . && rtk git commit -m "msg"`
- For debugging, use raw command without rtk prefix
- `rtk proxy <cmd>` runs command without filtering but tracks usage
<!-- /headroom:rtk-instructions -->

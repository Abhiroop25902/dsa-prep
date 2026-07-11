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

## Git workflow

After every plan update (progress logged, checklist ticked, stats synced), **commit and push automatically** — don't wait for the user to ask. Use a concise commit message summarizing what was solved/updated (e.g. "Day 2026-07-11: LC 424/20/704 solved, Sliding Window+Stack+Binary Search confirmed").

## Updating the file

- Append new Progress Tracker rows at the top of the table (newest first).
- If multiple problems are solved on the same date, merge them into one row with the date. List each problem in the Problem/Activity column and put timestamps + details in Notes.
- Keep the Stats Summary in sync when progress is logged.
- Don't reformat or restructure existing sections without being asked.

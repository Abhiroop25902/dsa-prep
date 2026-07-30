# AGENTS.md

Single markdown file (`abhiroop_faang_prep_plan.md`) — DSA + System Design interview prep tracker.
No code, no build, no tests, no CI. All work is updating the plan file.

## Mem0 Identity

Always include `user_id="abhiroopmukherjee"` and `app_id="Abhiroop25902-dsa-prep"` in every `search_memories` filter and `add_memory` call.

## Workflow

- **Session start:** `rtk git status` — if uncommitted changes exist from a prior day, commit them first: `rtk git add -A && rtk git commit -m "Day YYYY-MM-DD: carryover from previous session"`. Then read the plan file to pick up where you left off.
- **Commit after every problem solve.** After updating Progress Tracker, Stats Summary, and Currently Assigned: `rtk git add . && rtk git commit -m "Day YYYY-MM-DD: <problem> solved (<stats>)"`.
- Merge same-day problems into one row with timestamped entries.
- Only trust what's logged in the Progress Tracker. If user mentions unlogged progress, ask for confirmation.

## Communication

- **Weekdays:** report quick-stats (time taken, approach, issues/hints).
- **Weekends:** full interview-style walkthrough.
- User logs sessions as real-time timestamped traces (e.g. "6:31: trying X"). Read as diagnostic signal.
- Language: Java. Platform: LeetCode. Always include clickable LeetCode link when assigning a problem.
- **Never offer a menu** — just assign the next problem. User opts in for more.

## Key Conventions

- Progress Tracker: newest rows at top. Stats Summary: update periodically (not every session).
- Currently Assigned: update with next problem after each solve.
- Confidence: 1-5 scale, include with each logged problem.
- Recurring gaps to watch: Java collection API mixups (poll/peek, contains/isPresent), "adjacency list" vs "adjacency matrix" terminology.
- **`int[][]` sentinel gotcha:** `dp[i][j] == 0` conflates "uncomputed" with "answer is 0" — use `-1` sentinel. Already tripped on LC 64 and LC 516. Watch for this in any DP with valid 0 values.

## Session History

Keep a brief rolling log of key session decisions/outcomes for context continuity. Newest first.

| Date | Problems | Key Learnings |
|------|----------|---------------|
| 2026-07-30 | LC 516 — Longest Palindromic Subsequence | Center-expansion fails for subsequences — must shrink inward (`dp[i][j]` from `dp[i+1][j-1]`). -1 sentinel fix for int[][] cache. 31ms (80%). Moving to Greedy next. |
| 2026-07-27 | LC 5, LC 97 | BFS center-expansion for palindromic substrings. HashMap<String, Boolean> memo for Interleaving String. |
| 2026-07-25 | LC 63 | Start-position obstacle bug. |
| 2026-07-24 | LC 62, LC 64 | dp[i][j]==0 sentinel bug caught. |


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

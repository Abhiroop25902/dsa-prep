# Abhiroop's FAANG Interview Prep — Living Plan
*Last updated: 2026-08-03*

---

## Current State
- **Last solved:** LC 452 — Minimum Number of Arrows to Burst Balloons (2026-08-05, confidence 4.5/5)
- **Next problem:** [LC 763 — Partition Labels (Medium)](https://leetcode.com/problems/partition-labels/)
- **Current topic:** Greedy
- **Current phase:** Phase 1 — Pattern Reactivation
- **Problems solved since restart:** 44
- **Topic status:** Greedy — `in progress`; 2-D DP — `in progress`; all earlier sections — `confirmed/closed`
- **Active learning gaps:** Kadane's invariant intuition; 2-D DP memoization pattern recognition
- **Last session:** LC 452 completed independently; interval greedy now includes merging, earliest-endpoint retention, and intersection-based arrow grouping.

---

## For any Claude session reading this (read this part first)
This is Abhiroop Mukherjee's living DSA + System Design interview-prep tracker. If he's pasted this into a fresh chat, here's what to know before responding:

1. **Don't invent progress.** Trust the user's current message first; use `Current State` for the current pointer and the Progress Tracker for historical confirmation. If he mentions older unlogged progress, ask him to confirm/add it — don't assume or extrapolate.
2. **Time budget is 1-2 hrs/day, full-time job.** He's an Application Software Engineer 2 at Oracle (NetSuite/ERP stack), ~3 years experience. Keep suggestions sized to the Daily Structure section — don't pile on more.
3. **He is not a beginner.** His LeetCode history (557 problems in C++, 220 in Java, 95 in Python3, real depth in Dynamic Programming/Backtracking/Graphs, 500-day streak badge) shows a strong prior base that went rusty from ~2-3 years of enterprise work — not someone learning DSA from scratch. Reactivation and speed, not re-teaching fundamentals, is the job.
4. **Practice language is Java** (see Language Decision below) — default all code discussion to Java unless he says otherwise.
5. **When he reports a session**, append a row to the Progress Tracker and tick any completed checklist items. Update the Stats Summary periodically.
6. **This doc is a memory aid, not a contract.** If what he tells you now conflicts with what's written here, trust him — and update the doc accordingly.
7. Suggest he copy the updated document back into his notes every so often so state isn't lost between chats.

---

## Profile Snapshot
- **Role:** Application Software Engineer 2, Oracle India (previously Software Developer, Jul 2023–Jun 2026). Enterprise stack: NetSuite ERP (SuiteScript, UIF framework, SuiteQL, SuiteAnalytics), Java backends (JAX-RS, Guice), some TypeScript/React.
- **Education:** B.Tech CS, IIEST Shibpur, CGPA 9.64. Strong coursework in algorithms, graph theory, ML, and cryptography.
- **Publication:** "Detection of Cipher Types Using Machine Learning Techniques" (Springer, Aug 2023) — 96.72% accuracy across 5 cipher types using OPT Transformer multi-shot prompting.
- **Competitive programming:** Amazon ML Challenge 284th rank, Google Kickstart Round D 3176th rank.
- **LeetCode:** [abhi25902](https://leetcode.com/u/abhi25902/), global rank ~52,900. Historically solved 500+ problems total across languages, with genuine tagged depth in Dynamic Programming (114), Hash Table (192), DFS (113), Backtracking (33), Union-Find (28). Held 365-day and 500-day activity badges, most recent visible activity badge from 2024. Off LeetCode for the last couple of years.
- **Side projects already show real system-design instincts:** Sentinel (Pub/Sub-based decoupled ingestion, Spring WebFlux + virtual threads, horizontal scaling, TTL cleanup), Mindful Bites (multi-agent LangGraph DAG over Gemini), PCOD Nourish (Genkit tool-calling, Cloud Scheduler microservices). This is not nothing — most candidates prepping for system design rounds have never built anything like this.
- **Goal:** Applying to Master's programs; if that doesn't work out, job-hunting at FAANG-tier companies. DSA + System Design fluency serves both paths, so this plan is deliberately not tied to one outcome.
- **Full CV (LaTeX, always current):** [github.com/Abhiroop25902/cv](https://github.com/Abhiroop25902/cv)

---

## A Note on Rustiness
Pattern recognition — knowing that a problem is "sliding window" or "interval DP" — doesn't decay the way syntax does. That's why Phase 0 below is a diagnostic, not a restart from zero. What *has* shifted since you last practiced: Online Assessments increasingly wrap the same core algorithms in more elaborate scenario text, and system design interviews at AI-forward companies now sometimes include questions about LLM serving, RAG, or embedding pipelines — an area where your Mindful Bites and PCOD Nourish work actually puts you ahead of most candidates.

---

## Language Decision: Java
You asked whether to relearn C++ (stalled at classes/inheritance, no STL/smart-pointer depth) or lean into Java. **Go with Java.**
- You already have 220 problems solved in Java — a real head start, not a cold start.
- Zero context-switching: you write Java daily at work, so syntax and idioms are already muscle memory.
- Interview DSA rarely needs the C++ features you'd have to relearn (smart pointers, move semantics) — almost all interview-level C++ just uses STL containers, same role as Java's Collections framework (PriorityQueue, TreeMap, ArrayDeque cover the same ground).
- Every FAANG-tier company accepts Java for coding rounds.
- If a specific role explicitly wants C++ (some low-latency/systems teams), cross that bridge if it actually comes up — don't hedge against it now.

---

## Roadmap (~16 weeks to interview-ready, then indefinite maintenance)
**Actual pace note (updated 2026-07-08):** Phase 0 was scoped as "Week 1" but actually closed in ~5 calendar days (2026-07-03 to 2026-07-08), and Phase 1 started immediately after. The week numbers below are sizing guesses, not deadlines — moving faster than labeled is a good sign (fundamentals are more intact than the initial "3 years rusty" self-assessment suggested), but Phase 0 was inherently fast (6 targeted diagnostic problems) and Phase 1 covers much more ground (14 topics), so don't extrapolate the same compression rate without a few weeks of real Phase 1 data first.

### Phase 0 — Diagnostic & Setup (Week 1)
- Pick a comfortable Java practice setup (LeetCode's editor is fine; local IDE if you prefer running things yourself).
- Solve 6-8 problems spanning historically strong areas (DP, backtracking, graphs) and likely-rusty ones (tries, advanced Union-Find, trickier greedy) — timed, no hints.
- Log what came back instantly vs. what needed a nudge. **That becomes your real priority list**, not a generic topic order.

### Phase 1 — Pattern Reactivation (Weeks 2-6)
Work through NeetCode's roadmap (neetcode.io/roadmap) topic by topic, at *reactivation* speed:
Arrays & Hashing → Two Pointers → Sliding Window → Stack → Binary Search → Linked List → Trees → Heap/Priority Queue → Tries → Backtracking → Graphs (BFS/DFS/Union-Find/Topological Sort/Dijkstra) → 1-D DP → 2-D DP → Greedy & Intervals → Bit Manipulation.
Rule of thumb: if the diagnostic problem for a topic took under 15 min with a correct approach, just do 2-3 mediums to confirm and move on; if it needed a hint, do the full section.

### Phase 2 — Medium/Hard Depth (Weeks 7-10)
Timed mediums (target: correct approach within 20-25 min), plus hards specifically in your strongest historical areas (DP, Graphs) — those compound best in interviews. Start narrating your approach out loud before coding. That's the actual new skill here, not the algorithms themselves.

### Phase 3 — System Design Foundations (Weeks 8-14, overlaps Phase 2)
- **Spine:** Hello Interview's "System Design in a Hurry" (hellointerview.com) — delivery framework + core concepts (load balancing, caching, sharding, replication, CAP theorem, queues).
- **Depth:** ByteByteGo / Alex Xu (YouTube + books) for worked examples: rate limiter, URL shortener, chat system, news feed, distributed cache, web crawler.
- **Your differentiator:** lean into AI-system-design questions (LLM serving, RAG, embedding pipelines, GPU resource allocation) — you have real hands-on experience here. Don't undersell it.
- **Format:** pick a problem, timebox 45 min, draw it out (Excalidraw or paper), then check against a written breakdown.

### Phase 4 — Interview Simulation (Weeks 12-16+)
- **Mocks:** Pramp (now run through Exponent, tryexponent.com) for free-volume reps, 1-2/week. Add 1-2 paid Interviewing.io sessions in the final couple weeks before real interviews for calibrated, expert feedback.
- **Behavioral:** expand the Story Bank below into full STAR answers.
- **From Week 16 on — maintenance mode:** 3-4 problems/week to stay sharp, one system design problem every other week, and switch to loop-specific prep once real interviews are scheduled.

---

## Communication Format (agreed Day 1)
- **Weekdays:** report back quick-stats only — time taken, approach landed on, any issues/hints needed. No full walkthrough. Keeps sessions inside the 1-hr budget.
- **Once a week (tied to a weekend problem):** full interview-style walkthrough with the AI — talk through approach out loud, get pushed on trade-offs, simulate the real thing. AI will explicitly flag when it's time to go verbose.
- Real verbal-under-pressure reps come later from actual mocks (Pramp/Exponent) in Phase 4 — the weekly walkthrough here is a lighter-weight warmup for that, not a replacement.
- **How he logs sessions:** he writes a running timestamped log *as it happens* (e.g. "6:31: trying X", "6:46: found bug Y") rather than a cleaned-up summary after the fact. Read these as a real-time trace of his thinking, not a polished report — the messiness is useful diagnostic signal, don't ask him to reformat it. **Timing rule:** inline timestamps written *during* the attempt count as solve time (they're near-free, just narrating live thinking) — don't subtract these. Only the time between submission-accepted and message-sent (writing up the final recap) is overhead worth flagging/subtracting, and only when he calls it out.
- **Pacing philosophy (agreed 2026-07-08):** volume per sitting should increase progressively based on what's sustainable, not jump to match a single strong day. He did 3 problems in one sitting on 2026-07-08 and explicitly said not to treat that as the new baseline — the goal is gradually raising the daily default, not repeating a peak day and burning out. Don't assign multiple problems per weekday session by default; let him opt in if he has energy left, same as the weekend Redundant Connection/Kth Largest split earlier.
- **Links in chat:** always give the clickable LeetCode link directly in the chat message when assigning a problem — saves a back-and-forth.
- **No choices:** never offer a menu of problems — just assign the next one. He'll self-select if he wants more or wants to skip ahead; the AI shouldn't let him bias toward comfortable territory.

## Currently Assigned
**Topic:** Greedy
**Problem:** [LC 763 — Partition Labels (Medium)](https://leetcode.com/problems/partition-labels/)

**Phase 1 progress:** Greedy and 2-D DP are in progress. Arrays & Hashing, Two Pointers, Sliding Window, Stack, Binary Search, Linked List, Trees, Backtracking, Graphs, and 1-D DP are confirmed/closed. See the Progress Tracker for evidence and the Current State block for the current pointer.

---

## Daily Structure (fits 1-2 hrs/day)
**Weekdays (~1 hr):**
- 25-35 min: one problem, timed, no solutions until you've genuinely tried.
- 15-20 min: review — compare against the optimal solution if solved; read/watch the editorial if stuck, then re-implement from memory the next day.
- 2x/week once Phase 3 starts: swap one weekday problem slot for a system design article/video.

**Weekends (~1.5-2 hrs/day):**
- Day 1: two timed problems (mixed difficulty) + review.
- Day 2: system design deep-dive (read, then explain it back out loud) — or a mock interview every other week.

**Weekly total: ~7-9 hours** — matches your budget with room to breathe.

---

## Resource List
**DSA**
- NeetCode (neetcode.io) — curated roadmap + video breakdowns
- LeetCode (leetcode.com/u/abhi25902) — your existing account
- Striver's A2Z Sheet (takeuforward.org) — good second explanation style for weak topics

**System Design**
- Hello Interview (hellointerview.com) — delivery framework, built by former FAANG hiring managers
- ByteByteGo / Alex Xu — YouTube + books, best for worked examples
- Grokking the System Design Interview (Educative) — alternative course format

**Mock Interviews**
- Pramp / Exponent (tryexponent.com) — free peer-to-peer, good early-stage volume
- Interviewing.io — paid, FAANG-engineer feedback, best used close to real interviews

**Behavioral**
- Your own track record — see Story Bank below

---

## DSA Topic Checklist
- [x] Arrays & Hashing — confirmed 2026-07-08/09 (LC238, LC49)
- [x] Two Pointers — confirmed 2026-07-09/10 (LC11 - needed a hint, LC15 - self-debugged)
- [x] Sliding Window — confirmed 2026-07-11 (LC3 done, LC424 done)
- [x] Stack — confirmed 2026-07-11 (LC20 done)
- [x] Binary Search — confirmed 2026-07-11 (LC704 done)
- [x] Linked List — confirmed 2026-07-12 (LC206 + LC2 done)
- [x] Trees — confirmed 2026-07-15 (LC104 DFS, LC102 BFS, LC98 BST validation)
- [x] Heap / Priority Queue — tested Phase 0 (LC215), solid, first-ever Java PQ use
- [x] Tries — tested Phase 0 (LC208), gap was Java mechanics only, resolved same session
- [x] Backtracking
- [x] Graphs — Union-Find — tested Phase 0 (LC684), fully intact, no rust
- [x] Graphs — Topological Sort — tested + reinforced Phase 0 (LC207 → LC210), genuine new-concept gap closed
- [x] Graphs — BFS/DFS (general)
- [x] Graphs — Dijkstra/Shortest Path
- [x] 1-D Dynamic Programming — tested Phase 0 (LC300, 2/5), reinforced Phase 1 (LC198/70/213/322 — last 3 solved independently, 4-5/5). Section closed 2026-07-23.
- [ ] 2-D Dynamic Programming
- [ ] Greedy
- [ ] Intervals
- [ ] Bit Manipulation

## System Design Topic Checklist
- [ ] Delivery framework (requirements → API → high-level design → deep dives → bottlenecks)
- [ ] Load balancing
- [ ] Caching strategies
- [ ] Database sharding & replication
- [ ] CAP theorem & consistency patterns
- [ ] Message queues / event-driven design
- [ ] Rate limiting
- [ ] CDN & content delivery
- [ ] Worked problem: URL shortener
- [ ] Worked problem: Rate limiter
- [ ] Worked problem: Chat system
- [ ] Worked problem: News feed
- [ ] Worked problem: Distributed cache
- [ ] AI system design: LLM serving / RAG / embedding pipelines

---

## Progress Tracker
Append a new row after every session — newest at the top.

| Date | Phase | Topic | Problem/Activity | Time | Confidence (1-5) | Notes |
|------|-------|-------|-------------------|------|-------------------|-------|
| 2026-08-05 | Phase 1 | Greedy / Intervals | LC 452 — Minimum Number of Arrows to Burst Balloons (Medium, 4:59–5:10) | 11 min | 4.5/5 | Independently mapped the problem to interval intersection: sort by start, maintain the common intersection of the current arrow group, and start a new group when the next balloon is disjoint. Accepted in 60ms (7.93%), 95.58MB (69.87%). `O(n log n)` time from sorting; `O(n)` result-independent input/sort auxiliary space assumption as stated, with `O(1)` scan state. |
| 2026-08-03 | Phase 1 | Greedy / Intervals | LC 435 — Non-overlapping Intervals (Medium, 10:14–10:36) | 22 min | 4/5 | Initially chose the interval with the shorter range when overlaps were found; hint corrected the greedy invariant: retain the interval with the earlier end because it leaves maximum room for future intervals. Accepted in 61ms (7.71%), 115.87MB (39.55%). `O(n log n)` time from sorting; scan state is `O(1)`, though Java object-array sorting may use auxiliary space. |
| 2026-08-03 | Phase 1 | Greedy / Intervals | LC 57 — Insert Interval (Medium, 9:51–10:09) | 18 min | 4.5/5 | Independently derived the three-phase one-pass structure: append intervals before the new interval, merge all overlapping intervals, then append the remainder. Accepted in 1ms (98.19%), 46.99MB (76.22%). `O(n)` time and `O(n)` result space. |
| 2026-08-03 | Phase 1 | Greedy / Intervals | LC 56 — Merge Intervals (Medium, 9:37–9:47) | 10 min | 4.5/5 | Independently derived sort-by-start plus current-interval merging. Correct scan and overlap condition; accepted in 9ms (36.33%), 49.11MB (43.61%). Complexity correction: sorting makes total time `O(n log n)`; result storage is `O(n)`, while the merge scan uses `O(1)` auxiliary state. |
| 2026-08-02 | Phase 1 | Greedy | LC 45 — Jump Game II (Medium, 3:32–3:48) | ~16 min | 4.5/5 | Initially considered BFS and correctly recognized that explicit queue growth was unnecessary. Reframed BFS levels as contiguous jump frontiers: scan the current frontier and compute the farthest reach of the next jump, using O(1) state. Accepted: 1ms (99.73%), 47.09MB (88.85%). O(n) time, O(1) extra space. |
| 2026-08-02 | Phase 1 | Greedy | LC 55 — Jump Game (Medium, 3:23–3:26) | 3 min | 4.5/5 | Independently derived the greedy reachability scan: `idxReach` stores the farthest index reachable from all positions processed so far; if `i > idxReach`, the current index is unreachable and the answer is false. Correct O(n) time, O(1) extra space solution. Accepted: 2ms (88.66%), 47.39MB (98.75%). |
| 2026-08-02 | Phase 1 | Greedy | LC 53 — Maximum Subarray (Medium, 3:03–3:20) | ~17 min | 3.5/5 | Identified the naive O(n^3) range-sum approach and O(n^2) prefix-sum optimization, then rejected both for n=10^5. Needed a hint to reach Kadane's algorithm. Correct implementation: `runningSum` tracks the best subarray ending at the current index; reset before adding when the prior sum is negative. O(n) time, O(1) extra space. Intuition behind the invariant needs reinforcement. |
| 2026-07-30 | Phase 1 | 2-D DP | LC 516 — Longest Palindromic Subsequence (Medium, 6:12–7:00) | ~48 min | 3/5 | Center-expansion approach (ported from LC 5) doesn't naturally fit subsequences — recurrence should shrink inward, not expand outward. TLE bug: `int[][]` sentinel `0` conflated "uncomputed" with "answer is 0" (same gotcha as LC 64). Fixed with `-1` sentinel. 102ms (5.07%). |
| 2026-07-27 | Phase 1 | 2-D DP | LC 5 — Longest Palindromic Substring (Medium, 7:19–7:31); LC 97 — Interleaving String (Medium, 7:46–8:02+) | 12 min, ~20 min | 4/5, 2.5/5 | **LC 5:** BFS/queue center-expansion, self-derived. 49ms (30.64%), 46.22MB (40.62%). **LC 97:** DFS without memo → TLE on 106/107. Hint: subproblem is (s1Idx, s2Idx) since s3Idx = s1Idx+s2Idx. Fixed with `HashMap<String, Boolean>` cache (string key). Still hit `int[]` key Java gotcha same as LC 49. Accepted: 7ms (23.87%), 45.73MB (7.33%). Low confidence — 2-D DP memoization pattern recognition needs work. |
| 2026-07-26 | Phase 1 | 2-D DP | LC 72 — Edit Distance (Medium→Hard, 11:15–12:11, hint at 11:40) | 14 min solve (40 min elapsed incl. stuck time) | 3.5/5 | Confused on match-case: thought it needed +1 cost. Hint: when chars match, cost is 0 (carry diagonal forward). Once clicked, coded cleanly — base cases as string-to-empty distance, else min of insert/delete/replace+1. Accepted: 5ms (67.50th), 47.18MB (53.59th). Took too long for interview pace — string DP recurrence still needs reps. |
| 2026-07-25 | Phase 1 | 2-D DP | LC 63 — Unique Paths II (Medium, 10:58–11:07) | 9 min | 4/5 | Correct recurrence landed instantly: dp[i][j] = (recur(i+1,j) if not obstacle/bound) + (recur(i,j+1) if not obstacle/bound) — same grid DP pattern. Bug: missed start-position obstacle (return 0 if obstacleGrid[0][0]==1). Self-fixed. 5ms (2.82%), 43.44 MB (64.85%). |
| 2026-07-24 | Phase 1 | 2-D DP | LC 64 — Minimum Path Sum (Medium, 7:20–7:33); LC 62 — Unique Paths (Medium, 7:02–7:18) | 31 min total | 4/5, 4/5 | Two problems. **LC 62:** Top-down memoization, 0ms (100th). **LC 64:** Same grid pattern, added minimization. Bug: `dp[i][j]==0` guard fails when grid value is 0 — used `==0` sentinel, hit false reuse. Fixed. 1ms (99.93%). |
| 2026-07-23 | Phase 1 | 2-D DP | LC 1143 — Longest Common Subsequence (Medium) | ~37 min (6:21–6:58) | 3/5 | 2-D DP approach instant. Else-case bug: dp[i][j-1] only, missed dp[i-1][j] symmetry. Self-diagnosed after wrong-answer. Clean fix with Math.max of both skips. |
| 2026-07-23 | Phase 1 | 1-D DP | LC 322 — Coin Change (Medium) | 18 min (5:52–6:10) | 4/5 | Correct dp[i] = min(dp[i-coin] + 1) framing from the start. Self-debugged unreachable-amount handling. Clean final code, 14ms (90th percentile). Section closing — 5 problems done (LC300/198/70/213/322), last 3 solved independently. |
| 2026-07-22 | Phase 1 | 1-D DP | LC 213 — House Robber II (Medium) | ~10-15 min | 3.5/5 | Needed hint to reduce circle to two linear subproblems: rob(nums[0..n-2]) and rob(nums[1..n-1]). Initial 2D DP idea was directionally correct but overengineered. Once framed, code was clean. Used List for slicing (minor, O(n) extra copying). 0ms (100th percentile). Circle→linear reduction needs to be automatic next time. |
| 2026-07-22 | Phase 1 | 1-D DP | LC 70 — Climbing Stairs (Easy) | 11 min (5:47–5:58) | 5/5 | Initially thought 1 + dp[i-1] and 1 + dp[i-2] but caught duplicate-counting trap, manually derived dp[i] = dp[i-1] + dp[i-2] by walking small examples. Clean code, 0 bugs, 0ms (100th percentile). Good process: recognized flawed intuition → stepped back to examples → found correct recurrence independently. |
| 2026-07-21 | Phase 1 | 1-D DP | LC 198 — House Robber (Medium) | 13 min (5:01–5:14) | 4.5/5 | Correct recurrence on first thought: dp[i] = max(nums[i] + dp[i-2], dp[i-1]). Two self-debugged bugs: (1) dp[1] = nums[1] instead of max(nums[0], nums[1]), (2) initial attempt used maxDpTillI_2 tracking (unnecessary for standard House Robber — dp[i-2] already contains optimal). Clean textbook solution after fix: 0ms (100th percentile). Strong signal — jumped straight to correct dp[i] framing with no hints, first time doing that for a DP problem. |
| 2026-07-21 | Phase 1 | 1-D DP | LC 300 — Longest Increasing Subsequence (Medium, reinforcement rep) | 4 min (incl. ~10 min stuck before hint) | 3.5/5 | Recursion→tabulation gap narrowed significantly. Needed hint to reframe state as `dp[i]` = LIS ending at i (dropped tracking prev_index + count). Once framed, code was instant — 0 bugs, clean O(n²). Compare: Phase 0 same problem = 60 min + couldn't close without full solution walkthrough. One more rep should make this independent. |
| 2026-07-19 | Phase 1 | Graphs — Dijkstra/Shortest Path | LC 743 — Network Delay Time (Medium) | 27 min | 4/5 | Implemented Dijkstra's algorithm with adjacency list and priority queue. Initial bug in weight indexing fixed; corrected logic to allow re-queuing nodes with shorter paths. Accepted: 177 ms (beats 5.06%), 49.76 MB (beats 22.86%). Noted potential micro-optimizations (reducing wrapper classes) but prioritized correctness first. |
| 2026-07-19 | Phase 1 | Graphs BFS/DFS | LC 200 — Number of Islands (Medium, graph DFS with in-place modification) | 15 min | 4/5 | Started with visited[][] approach (minor bugs fixed), switched to in-place grid modification for O(1) extra space. Accepted: 3 ms (beats 87.98%), 52.42 MB (beats 33.82%). Demonstrated DFS traversal, grid mutation technique, and complexity analysis. Graphs BFS/DFS section confirmed. |
| 2026-07-18 | Phase 1 | Trees / Backtracking | LC 226 — Invert Binary Tree (Easy, 2 min, 0 bugs); LC 46 — Permutations (Medium, 20 min, 0 bugs, optimized to boolean[] post-submit); LC 78 — Subsets (Medium, 15 min, 0 bugs, take-or-not-take, 1ms) | ~37 min total | 5/5, 3/5→4/5, 4/5 | Three problems. **LC 226:** trivial confirm, trees closed. **LC 46:** HashSet+Set.copyOf first, then optimized to boolean[] used — standard template locked in. **LC 78:** take-or-not-take pattern, clean and fast. Two distinct backtracking templates confirmed: used-array (permutations) and take-or-skip (subsets). Next: Graphs BFS/DFS (LC 200). |
| 2026-07-15 | Phase 1 | Trees | LC 104 — Maximum Depth of Binary Tree (Easy, 9 min, 0 bugs, 100th percentile); LC 102 — Binary Tree Level Order Traversal (Medium, 10 min, 0 bugs, 96th percentile); LC 98 — Validate BST (Medium, 23 min, 2 self-debugged bugs, 100th percentile) | ~42 min total | 4/5, 4/5, 3/5 | Three problems, one sitting. **LC 104:** DFS recursive, clean. **LC 102:** BFS with ArrayDeque, level-by-level via levelSize snapshot. **LC 98:** Recursive bounds validation. Two real BST traps hit: (1) only checked immediate parent nodes instead of propagating bounds through entire subtree — rewrote to pass min/max down correctly; (2) used Integer.MIN/MAX_VALUE as boundary sentinels which fails when tree contains actual min/max ints — fixed by switching to Long. Both self-diagnosed without hints. Trees section well covered: DFS, BFS, and BST validation all confirmed. |
| 2026-07-12 | Phase 1 | Linked List | LC 2 — Add Two Numbers (Medium) | 10 min (8:51-9:01 PM, 1 self-debugged bug, confidence 5/5) | 5/5 | Recursive solution with carry propagation — handled unequal-length lists and final carry correctly. One bug: missed the case where both lists are null but carry > 0, self-diagnosed and fixed. Runtime 100th percentile (1 ms). Code note: two overloaded methods with duplicated logic; idiomatic fix is single public method delegating to a private helper with carry param (same pattern as LC 208 insert). Linked List medium confirm done — **section closed.** |
| 2026-07-11 | Phase 1 | Sliding Window / Stack / Binary Search / Linked List | LC 424 — Longest Repeating Character Replacement (47 min, 12:15-1:02 PM, 3 self-debugged bugs, confidence 3/5); LC 20 — Valid Parentheses (9 min, 2:08-2:17 PM, 1 self-debugged bug, confidence 4/5); LC 704 — Binary Search (8 min, 2:25-2:33 PM, 1 self-debugged bug, confidence 5/5); LC 206 — Reverse Linked List (3 min, 3:25-3:28 PM, 0 bugs, confidence 5/5) | ~67 min total | 3/5, 4/5, 5/5, 5/5 | Four problems, one sitting. **LC 424:** Correct sliding window + frequency-count approach derived independently. Key insight: swapsRequired = windowLength - maxFrequency. Bugs: wrong right increment condition, missing initial char save into map, off-by-one in array size — all self-diagnosed. TC O(n*26), SC O(1). Runtime 19th percentile. **LC 20:** Clean stack implementation using ArrayList. Researched Stack vs ArrayList first — correctly identified thread-safety overhead as reason to avoid java.util.Stack. One bug: forgot empty-stack check before accessing top. Runtime 87th percentile. **LC 704:** Correctly recalled overflow fix (left + (right-left)/2), noted compiler optimizes /2 to bit-shift. Made insightful observation that binary search is "two pointers that converge." One typo bug (mid vs nums[mid]). Runtime 100th percentile. All three prior sections confirmed and closed. **LC 206:** Three-pointer iterative reversal (back/curr/front) recalled from memory with zero friction. 3 min, 0 bugs, 100th percentile. Linked List fundamentals confirmed intact — next: medium confirm (LC 2). |
| 2026-07-10 | Phase 1 | Two Pointers / Sliding Window | LC 15 — 3Sum (~20 min, 8:30-8:50 PM, 5 self-debugged bugs, confidence 3/5); LC 3 — Longest Substring Without Repeating Characters (10 min, 9:13-9:23 PM, confidence 4/5) | ~30 min total | 3/5, 4/5 | Two problems, one sitting. **LC 15:** Correctly transferred sort + two-pointer pattern from Two Sum unprompted. Solved duplicate-triplet dedup via HashSet<List<Integer>> (valid but not standard). All bugs self-diagnosed without hints — good debugging trace, if slow (5 rounds). Real gap: only moved left++ after match, never right--, causing redundant rescanning on duplicate-heavy input. Post-session: implemented standard duplicate-skip optimization and verified empirically — Set→List (962ms→544ms), then explicit skip logic (544→32ms). **LC 3:** Fast, immediate pattern transfer from Two Pointers ("same two-pointer approach, different rule for moving them"). All bugs minor typos/off-by-ones, no conceptual issues. Two Java vocabulary gaps resolved: boxed wrapper types for generics (Character, not char), and contains() as the membership-check idiom. Two Pointers confirmed (LC11 needed hint, LC15 self-debugged); Sliding Window started (LC3 = first confirm). |
| 2026-07-09 | Phase 1 | Two Pointers | LC 11 - Container With Most Water (Java) | 19 min (7:25-7:44 PM, incl. ~9 min pre-hint) | 3/5 | Excellent reasoning before the hint: found the area formula immediately, correctly ruled out the compare-both-directions DP-style approach as O(n²), and validated against the 10^5 constraint to confirm O(n²) would TLE before asking for help — exactly the right formula→complexity-budget→elimination sequence for an interview. The actual gap was a specific unseen insight, not general two-pointer weakness: "always move the shorter/limiting pointer inward, moving the taller one can never win" is a classic non-obvious greedy-elimination proof most people need to see once. Post-hint, excellent self-validation against mountain and valley shapes before coding — good habit to keep. Code correct and optimal (O(n)/O(1)) but added an unnecessary equal-height tie-break branch (ties can go either direction safely) containing a bounds check that's actually unreachable given the loop's own `left < right` invariant — worth noticing the difference from the earlier Course Schedule assertions, which guarded real invariants rather than an already-impossible case. Follow-up discussion: he pushed back defending the tie-break logic (checking next-heights to minimize height reduction) — walked through the rigorous discard proof (`height[left] <= height[right]` ⟹ area(left,k) < area(left,right) for all k between them, provably not just probably), which shows both directions are simultaneously valid on a tie, so look-ahead adds no value. Good habit that he questioned it rather than just accepting the simplification — worth remembering he responds well to proofs, not just assertions. |
| 2026-07-09 | Phase 1 | Arrays & Hashing | LC 49 - Group Anagrams (Java) | 18 min (7:01-7:19 PM) | 4/5 | Strong reasoning, not just a solve: tried Map<int[], String> first, correctly diagnosed *why* it fails (arrays use reference equality for equals/hashCode, not value equality), and pivoted to List<Integer> as the key — a genuinely subtle Java gotcha, understood via investigation not memorization. One off-by-one bug (`i < 'z'-'a'` vs `i <= 'z'-'a'`) self-fixed quickly. Complexity stated close but needed tightening: correct order is O(n·m) time (n=word count, m=max length) and O(n·m) space (not O(n) — output strings must be stored, same total chars as input), and don't mix asymptotic notation with literal byte counts in the same expression. Arrays & Hashing confirm now covers both prefix/suffix (LC238) and hashing (LC49) sides — both fast/solid, section can close per the 2-3 confirm rule. Moving to Two Pointers next. |
| 2026-07-08 | Phase 0 → Phase 1 | Graphs — Topological Sort / Arrays & Hashing | LC 210 — Course Schedule II (~30 min active, 6:22-6:53 PM, confidence 4/5); LC 238 — Product of Array Except Self (14 min, 7:10-7:24 PM, confidence 5/5) | ~44 min total | 4/5, 5/5 | Two problems, one sitting. **LC 210:** Reinforcement rep — down from 46 min to 30 min on same technique. Kahn's algorithm recalled with zero hesitation (vs researching from scratch previous night). All bugs mechanical: indegree-increment-on-wrong-node bug (self-debugged), poll()/peek() mixup (inverted from previous night's confusion). Repeated "adjacency matrix" vs "adjacency list" terminology slip — needs to lock in this time. Intentional naming (targetCourse/requirementCourse), correctly judged O(V) index tracker not worth the complexity vs O(V+E) dominated. **LC 238:** Fast and clean — caught division-by-zero trap before coding, landed on prefix/suffix technique immediately. Proactively identified O(1)-space follow-up unprompted. Strongest area so far, right at the "under 15 min, skip ahead" threshold. Phase 0 closed, Phase 1 began. |
| 2026-07-08 | Phase 0 | Graphs - Topological Sort | LC 207 - Course Schedule (Java) | ~46 min (12:38-1:24 AM) | 2/5 | Different category from every prior Phase 0 entry: this was genuine new-concept learning, not reactivation — had zero prior exposure to topological sort/Kahn's algorithm and correctly said so upfront. Strong process despite the gap: reasoned through why a naive BFS wouldn't work, researched Kahn's algorithm (idea only, not code), correctly recognized the problem only needs cycle detection so a node-indegree BFS is the right shape, self-debugged an indegree-vs-node-value bug, and discovered Queue is an interface requiring ArrayDeque. Correct O(V+E) time solution, accepted (6ms/47.3MB). Needs a reinforcement rep (e.g. Course Schedule II) before this is interview-solid — tonight closed the knowledge gap, reps will close the speed gap. Also corrected: code builds an adjacency list (O(V+E) space), not a matrix (O(V²)) — flagged as an important distinction to retain. |
| 2026-07-06 | Phase 0 | Union-Find | LC 684 - Redundant Connection (Java) | ~10 min (7:04-7:15 PM, incl. 1 compile-error submit) | 5/5 | Fully intact — no rust here at all, unlike DP/Tries. Correctly recalled path compression from memory and implemented it cleanly on effectively the first real attempt (compile error was a param mismatch, not a logic error). Proactively recalled union-by-rank/size *and* correctly judged it unnecessary for this problem (n nodes + 1 extra edge → shallow recursion regardless) — strong interview-relevant judgment call, the kind worth stating out loud in a real interview. Result: 1ms runtime (beats 91.57%), 44.96MB memory (beats 68.19%). |
| 2026-07-05 | Phase 0 | Heap/PQ | LC 215 - Kth Largest Element (Java) | 12 min (5:40-5:52 PM) | 4/5 | First-ever use of Java's PriorityQueue (no work exposure) — looked up the API cold and got a correct, working max-heap solution fast. Strong signal: correctly recalled quickselect from memory (partition-to-final-position, recurse on the side containing k) unprompted — non-trivial technique to retain, just rusty on implementation. Attempted the more idiomatic size-k min-heap version first, hit an error, and deliberately reverted to the simpler O(n log n) max-heap version in the interest of time rather than debugging further — correctly identified as the right call for Phase 0 (working solution + naming the better approach beats burning time chasing optimal right now). C++→Java queue API gap surfaced: knew push/pop/top (C++), didn't know poll()/offer()/peek() (Java) — noted as a translation table to internalize. Self-flagged a recurring pattern twice today (guessed at unstated Trie API, guessed at startsWith edge-case behavior) — good self-awareness; the fix is to state assumptions out loud before coding, same as asking an interviewer to confirm. |
| 2026-07-04 | Phase 0 | Tries | LC 208 - Implement Trie (Java) | 37 min (4:56-5:33 PM) | 3/5 | Genuinely unknown territory (no prior Trie exposure) but structure came together correctly with zero conceptual stumbles — all friction was Java-mechanics (variable shadowing between param and field, no default params in Java, array-length vs string-length confusion). Different flavor of gap than DP: this is language-idiom rust, not DSA-concept rust. Code review flagged: startsWith over-engineered (doesn't need the extra search() call or child-check loop), and zero-arg overloads duplicated logic instead of delegating to the charIdx version (root cause of the confusing this.word bug). Self-diagnosed root causes well: added unnecessary `word` field from guessing at an unstated prefix-listing API instead of reading the full method list first; missed `fn(word, 0)` delegation because Lombok's `@Default` normally handles that at work — habit gap, not a knowledge gap. |
| 2026-07-03 | Phase 0 | DP | LC 300 - Longest Increasing Subsequence (Java, O(n²)) | ~60 min active (65 min elapsed − 5 min break) | 2/5 | Recursion (take/skip) came fast (~11 min), but recursion→bottom-up-table translation didn't click on its own — needed a hint on the `dp[i]` = LIS ending at i framing. Independently derived the "patience sorting / tails" dominance-pruning idea from first principles before being taught it — strong signal the underlying DP intuition is intact. Real gap identified: recursive-DP → tabulation translation fluency, not DP concepts themselves. Also flagged: comfort with `int[]` vs `List<Integer>` needs reps — reached for List by habit. |

## Stats Summary
*(periodic snapshot — last synced 2026-08-03)*
- Total problems solved since restart: 44 (LC300/198/208/215/684/207/210/238/49/11/15/3/424/20/704/206/2/104/102/98/226/46/78/200/743/322/1143/62/64/63/72/5/97/53/55/45/56/57/435/452)
- Current phase: Phase 1 — Pattern Reactivation. Greedy and 2-D DP are in progress.
- Weakest topic: formerly DP — now climbing. 1-D DP closed (5 problems). 2-D DP in progress (LC1143/62/64/63/72/5).
- Strongest topics: Union-Find (5/5), Arrays & Hashing (5/5, 4/5), Linked List (5/5), Trees (5/5), 1-D DP (4/5 on final solves)
- Recurring pattern to watch: Java collection API mixups (poll/peek, contains/isPresent) and "adjacency list" vs "adjacency matrix" terminology

---

## Behavioral Story Bank (STAR format)
Seeded from your resume — genuinely strong, quantified material. Flesh each into full Situation/Task/Action/Result as you prep.

1. **SuiteQL migration (impact/performance):** Converted Saved Search-based data retrieval to SuiteQL, cutting data-fetch latency 20% and reducing large-dataset load time from 1+ minute to ~2 seconds via pagination.
2. **CI quality improvement (ownership/process):** Raised Benchmark 360's CI automation pass rate from 68.5% to 91.22% by adding Groovy/XPath browser automation coverage.
3. **Hackathon (initiative, execution under pressure):** Top 30 worldwide, Top 3 in India, Oracle NetSuite's Global AI Hackathon — LLM-powered analytics assistant.
4. **EVE Healthcare (ambiguity, startup pace):** Built a production mobile app as part of a 3-person team that contributed to $37,000 in revenue on launch day.
5. **Cross-account integration discovery (technical judgment without a clean answer):** Evaluated RESTlet/SuiteTalk approaches and token-based auth for cross-account NetSuite integration, documenting scalability risks for future teams.

**Gaps to add:** a conflict-with-a-teammate story, a time you disagreed with a decision, and a failure/mistake story — these are the ones most candidates haven't prepped and get caught flat-footed on.

---

## How to Use This Document
1. Keep this as one durable file (Notes app, Google Doc, plain `.md` — whatever you'll actually maintain).
2. Starting a fresh chat? Paste this whole document in first.
3. After a session, tell the AI what you did and ask for the doc back with the Progress Tracker and Stats Summary updated — paste that version back into your note.
4. Treat the Roadmap's week numbers as a guide, not a deadline. Move on when the checklist feels solid, not when the calendar says so.

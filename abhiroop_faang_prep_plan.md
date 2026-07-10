# Abhiroop's FAANG Interview Prep — Living Plan
*Last updated: 2026-07-10 (Day 11 — Phase 1, Sliding Window in progress)*

---

## For any Claude session reading this (read this part first)
This is Abhiroop Mukherjee's living DSA + System Design interview-prep tracker. If he's pasted this into a fresh chat, here's what to know before responding:

1. **Don't invent progress.** Only trust what's logged in the Progress Tracker below. If he mentions doing something that isn't logged, ask him to confirm/add it — don't assume or extrapolate.
2. **Time budget is 1-2 hrs/day, full-time job.** He's an Application Software Engineer 2 at Oracle (NetSuite/ERP stack), ~3 years experience. Keep suggestions sized to the Daily Structure section — don't pile on more.
3. **He is not a beginner.** His LeetCode history (557 problems in C++, 220 in Java, 95 in Python3, real depth in Dynamic Programming/Backtracking/Graphs, 500-day streak badge) shows a strong prior base that went rusty from ~2-3 years of enterprise work — not someone learning DSA from scratch. Reactivation and speed, not re-teaching fundamentals, is the job.
4. **Practice language is Java** (see Language Decision below) — default all code discussion to Java unless he says otherwise.
5. **When he reports a session**, append a row to the Progress Tracker and tick any completed checklist items. Update the Stats Summary periodically.
6. **This doc is a memory aid, not a contract.** If what he tells you now conflicts with what's written here, trust him — and update the doc accordingly.
7. Suggest he copy the updated document back into his notes every so often so state isn't lost between chats.

---

## Profile Snapshot
- **Role:** Application Software Engineer 2, Oracle India (previously Software Developer, Jul 2023–Jun 2026). Enterprise stack: NetSuite ERP (SuiteScript, UIF framework, SuiteQL, SuiteAnalytics), Java backends (JAX-RS, Guice), some TypeScript/React.
- **Education:** B.Tech CS, IIEST Shibpur, CGPA 9.64. Strong coursework in algorithms, graph theory, ML, and cryptography (published paper on cipher-type detection).
- **LeetCode:** [abhi25902](https://leetcode.com/u/abhi25902/), global rank ~52,900. Historically solved 500+ problems total across languages, with genuine tagged depth in Dynamic Programming (114), Hash Table (192), DFS (113), Backtracking (33), Union-Find (28). Held 365-day and 500-day activity badges, most recent visible activity badge from 2024. Off LeetCode for the last couple of years.
- **Side projects already show real system-design instincts:** Sentinel (Pub/Sub-based decoupled ingestion, Spring WebFlux + virtual threads, horizontal scaling, TTL cleanup), Mindful Bites (multi-agent LangGraph DAG over Gemini), PCOD Nourish (Genkit tool-calling, Cloud Scheduler microservices). This is not nothing — most candidates prepping for system design rounds have never built anything like this.
- **Goal:** Applying to Master's programs; if that doesn't work out, job-hunting at FAANG-tier companies. DSA + System Design fluency serves both paths, so this plan is deliberately not tied to one outcome.

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

## C++ → Java Quick Reference (running list, add as new gaps surface)
Collected from actual mid-problem friction points — the goal is to stop re-discovering the same thing twice.

- **Queue operations:** C++ `push()`/`pop()`/`top()` → Java `offer()`/`poll()`/`peek()`. Memory aid: "poll" *pulls* something out (removes), "peek" just looks (doesn't remove).
- **Set/Map membership check:** C++ `s.find(x) != s.end()` (or C++20's `s.contains(x)`) → Java `s.contains(x)` directly. (Not to be confused with `Optional.isPresent()`, which is unrelated — different "does this hold something" question.)
- **No default parameters in Java.** C++/Lombok-style defaults don't exist natively — the idiomatic fix is method overloading where the shorter signature delegates to the fuller one, e.g. `insert(word) { insert(word, 0); }`, not reimplementing the logic twice.
- **Primitives can't go directly into generics.** `Set<char>` isn't legal — use the boxed wrapper: `int`→`Integer`, `char`→`Character`, `boolean`→`Boolean`, etc. General rule, not just one type.
- **Arrays use reference equality for `equals()`/`hashCode()`**, so `int[]` can't be used as a meaningful `HashMap`/`HashSet` key (two arrays with identical contents are still "different" keys) — use `List<Integer>` instead, which has value-based equality.
- **`Queue` is an interface, not a class** — instantiate with `new ArrayDeque<>()` (or `LinkedList<>()`), not `new Queue<>()`.
- **List vs. array length:** `.size()` for `List`/collections, `.length` for arrays (property, not method), `.length()` for `String` (method). Three different syntaxes for "how big is this."

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

## Currently Assigned
**Two Pointers is now confirmed and closed** (LC11 - needed a hint on the discard-proof insight, LC15 - self-debugged to AC without a hint). Moving to **Sliding Window** per the Phase 1 roadmap order.

**Day 12 (next session):**
- Problem: [Longest Repeating Character Replacement — LeetCode 424 (Medium)](https://leetcode.com/problems/longest-repeating-character-replacement/)
- Why: second Sliding Window confirm — LC3 went fast (10 min) but was a fairly standard variable-window shape; this one adds a frequency-count + "can I still expand given k replacements allowed" twist, a good second data point before closing the section per the 2-3 confirm rule.
- Language: Java, timed 20-25 min, no hints/editorial
- Report back: time taken, approach, confidence 1-5

**Day 11 result (2026-07-10, 9:13 PM):** LC 3 (Longest Substring Without Repeating Characters) — solved in 10 min, confidence 4/5. Fast, clean pattern transfer from Two Pointers. See Progress Tracker for detail.
- *(Clear the Day 11 line once Day 12 is reported and this rolls forward)*

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
- [ ] Sliding Window — in progress, 1/2 confirms done (LC3 done, LC424 assigned)
- [ ] Stack
- [ ] Binary Search
- [ ] Linked List
- [ ] Trees (traversals, BST)
- [x] Heap / Priority Queue — tested Phase 0 (LC215), solid, first-ever Java PQ use
- [x] Tries — tested Phase 0 (LC208), gap was Java mechanics only, resolved same session
- [ ] Backtracking
- [x] Graphs — Union-Find — tested Phase 0 (LC684), fully intact, no rust
- [x] Graphs — Topological Sort — tested + reinforced Phase 0 (LC207 → LC210), genuine new-concept gap closed
- [ ] Graphs — BFS/DFS (general)
- [ ] Graphs — Dijkstra/Shortest Path
- [ ] 1-D Dynamic Programming — tested Phase 0 (LC300), real unresolved gap (recursion→tabulation translation), needs a reinforcement rep when Phase 1 reaches DP
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
| 2026-07-10 | Phase 1 | Sliding Window | LC 3 - Longest Substring Without Repeating Characters (Java) | 10 min (9:13-9:23 PM) | 4/5 | Fast, immediate pattern transfer from Two Pointers ("same two-pointer approach, different rule for moving them" — exactly right mental model). All bugs were minor typos/off-by-ones, no conceptual issues. Two Java vocabulary gaps surfaced and resolved via lookup: boxed wrapper types needed for generics (Character, not char), and contains() as the Java membership-check idiom (he was thinking of C++'s find()!=end() / C++20's contains()). Structural note: `ans` update sits at the top of the loop (measuring the previous iteration's window), which is why a trailing post-loop update was needed and why the off-by-one bug happened — moving the update to right after `right++` inside the loop is the more standard, less fragile idiom; not urgent to refactor this one, but worth adopting going forward. |
| 2026-07-10 | Phase 1 | Two Pointers | LC 15 - 3Sum (Java) | ~20 min (8:30-8:50 PM, 5 self-debugged bugs, no external hint needed) | 3/5 | Correctly transferred the sort + two-pointer pattern from Two Sum unprompted, and independently solved the duplicate-triplet problem via a HashSet<List<Integer>> dedup — a valid approach, though not the standard one. Every bug (array bounds, missing loop-break, variable typos) was self-diagnosed and fixed without a hint — good debugging trace, if slow (5 rounds). Real gap: only moved `left++` after a match, never `right--`, causing redundant rescanning on duplicate-heavy input, compounded by HashSet's per-insert hashing overhead on boxed Lists — explains the poor 962ms/6.68th-percentile runtime despite correct O(n²) Big-O. Walked through the standard fix: skip duplicate `i`/`left`/`right` explicitly on a sorted array (move both pointers on a match, then skip forward past repeats) instead of dedup-by-Set — same asymptotic complexity, much better constant factor, no hashing needed. Two Pointers now has 2 confirms (LC11 needed a hint, LC15 self-debugged to AC) — section can close, moving to Sliding Window next. **Follow-up (same session):** implemented the suggested optimization himself and empirically verified both wins separately — Set→List (962ms→544ms, removed hashing overhead) and adding explicit duplicate-skip logic (544ms→32ms, removed redundant rescanning) — strong self-driven verification, not just a passing solve. Also repeated the same unreachable-bounds-guard pattern as LC11 (`left>=length \|\| right<0` check that the loop's own condition already prevents) — worth a standing mental note to check the loop invariant before adding a defensive guard. |
| 2026-07-09 | Phase 1 | Two Pointers | LC 11 - Container With Most Water (Java) | 19 min (7:25-7:44 PM, incl. ~9 min pre-hint) | 3/5 | Excellent reasoning before the hint: found the area formula immediately, correctly ruled out the compare-both-directions DP-style approach as O(n²), and validated against the 10^5 constraint to confirm O(n²) would TLE before asking for help — exactly the right formula→complexity-budget→elimination sequence for an interview. The actual gap was a specific unseen insight, not general two-pointer weakness: "always move the shorter/limiting pointer inward, moving the taller one can never win" is a classic non-obvious greedy-elimination proof most people need to see once. Post-hint, excellent self-validation against mountain and valley shapes before coding — good habit to keep. Code correct and optimal (O(n)/O(1)) but added an unnecessary equal-height tie-break branch (ties can go either direction safely) containing a bounds check that's actually unreachable given the loop's own `left < right` invariant — worth noticing the difference from the earlier Course Schedule assertions, which guarded real invariants rather than an already-impossible case. Follow-up discussion: he pushed back defending the tie-break logic (checking next-heights to minimize height reduction) — walked through the rigorous discard proof (`height[left] <= height[right]` ⟹ area(left,k) < area(left,right) for all k between them, provably not just probably), which shows both directions are simultaneously valid on a tie, so look-ahead adds no value. Good habit that he questioned it rather than just accepting the simplification — worth remembering he responds well to proofs, not just assertions. |
| 2026-07-09 | Phase 1 | Arrays & Hashing | LC 49 - Group Anagrams (Java) | 18 min (7:01-7:19 PM) | 4/5 | Strong reasoning, not just a solve: tried Map<int[], String> first, correctly diagnosed *why* it fails (arrays use reference equality for equals/hashCode, not value equality), and pivoted to List<Integer> as the key — a genuinely subtle Java gotcha, understood via investigation not memorization. One off-by-one bug (`i < 'z'-'a'` vs `i <= 'z'-'a'`) self-fixed quickly. Complexity stated close but needed tightening: correct order is O(n·m) time (n=word count, m=max length) and O(n·m) space (not O(n) — output strings must be stored, same total chars as input), and don't mix asymptotic notation with literal byte counts in the same expression. Arrays & Hashing confirm now covers both prefix/suffix (LC238) and hashing (LC49) sides — both fast/solid, section can close per the 2-3 confirm rule. Moving to Two Pointers next. |
| 2026-07-08 | Phase 1 | Arrays & Hashing | LC 238 - Product of Array Except Self (Java) | 14 min (7:10-7:24 PM) | 5/5 | Fast and clean — confirms Arrays is his strongest area, right at the "under 15 min, skip ahead" threshold from the Phase 1 rule. Caught the division-by-zero trap before coding, landed on prefix/suffix technique immediately, one trivial compile typo only. Proactively identified the O(1)-space follow-up (fill output array in forward pass, single running suffix scalar in backward pass) unprompted and correctly — strong interview signal, most people stop at the working O(n) solution. |
| 2026-07-08 | Phase 0 | Graphs - Topological Sort (reinforcement) | LC 210 - Course Schedule II (Java) | ~30 min active (6:22/23 PM start - 6:53 PM accepted; excludes ~5 min recap message writing per his request) | 4/5 | Reinforcement rep worked as intended — down from 46 min to 30 min on the same underlying technique, Kahn's algorithm recalled with zero hesitation this time (vs. needing to research it from scratch last night). All bugs today were mechanical, not conceptual: MLE + wrong answer both traced to a transient indegree-increment-on-wrong-node bug (self-debugged), plus a poll()/peek() mixup — notably inverted from last night's confusion (didn't know they existed → knew they existed but assigned wrong behavior to each), worth a deliberate memory aid. Repeated the "adjacency matrix" vs "adjacency list" terminology slip from yesterday — same code structure (List<List<Integer>>), still O(V+E) not O(V²), needs to lock in this time. Also repeated yesterday's negative-indegree check — clarified afterward as an intentional fail-fast assertion (invariant check), not dead code as this tracker originally (incorrectly) framed it; a good defensive habit, and the interview-relevant move is to say the reasoning out loud ("shouldn't happen given the invariants, guarding in case of a bug elsewhere"). Genuinely good: intentional naming (targetCourse/requirementCourse), and correctly reasoned that trading visitingOrder for a manual index tracker isn't worth it since O(V) is dominated by O(V+E) regardless — real algorithmic judgment, not just code-writing. |
| 2026-07-08 | Phase 0 | Graphs - Topological Sort | LC 207 - Course Schedule (Java) | ~46 min (12:38-1:24 AM) | 2/5 | Different category from every prior Phase 0 entry: this was genuine new-concept learning, not reactivation — had zero prior exposure to topological sort/Kahn's algorithm and correctly said so upfront. Strong process despite the gap: reasoned through why a naive BFS wouldn't work, researched Kahn's algorithm (idea only, not code), correctly recognized the problem only needs cycle detection so a node-indegree BFS is the right shape, self-debugged an indegree-vs-node-value bug, and discovered Queue is an interface requiring ArrayDeque. Correct O(V+E) time solution, accepted (6ms/47.3MB). Needs a reinforcement rep (e.g. Course Schedule II) before this is interview-solid — tonight closed the knowledge gap, reps will close the speed gap. Also corrected: code builds an adjacency list (O(V+E) space), not a matrix (O(V²)) — flagged as an important distinction to retain. |
| 2026-07-06 | Phase 0 | Union-Find | LC 684 - Redundant Connection (Java) | ~10 min (7:04-7:15 PM, incl. 1 compile-error submit) | 5/5 | Fully intact — no rust here at all, unlike DP/Tries. Correctly recalled path compression from memory and implemented it cleanly on effectively the first real attempt (compile error was a param mismatch, not a logic error). Proactively recalled union-by-rank/size *and* correctly judged it unnecessary for this problem (n nodes + 1 extra edge → shallow recursion regardless) — strong interview-relevant judgment call, the kind worth stating out loud in a real interview. Result: 1ms runtime (beats 91.57%), 44.96MB memory (beats 68.19%). |
| 2026-07-05 | Phase 0 | Heap/PQ | LC 215 - Kth Largest Element (Java) | 12 min (5:40-5:52 PM) | 4/5 | First-ever use of Java's PriorityQueue (no work exposure) — looked up the API cold and got a correct, working max-heap solution fast. Strong signal: correctly recalled quickselect from memory (partition-to-final-position, recurse on the side containing k) unprompted — non-trivial technique to retain, just rusty on implementation. Attempted the more idiomatic size-k min-heap version first, hit an error, and deliberately reverted to the simpler O(n log n) max-heap version in the interest of time rather than debugging further — correctly identified as the right call for Phase 0 (working solution + naming the better approach beats burning time chasing optimal right now). C++→Java queue API gap surfaced: knew push/pop/top (C++), didn't know poll()/offer()/peek() (Java) — noted as a translation table to internalize. Self-flagged a recurring pattern twice today (guessed at unstated Trie API, guessed at startsWith edge-case behavior) — good self-awareness; the fix is to state assumptions out loud before coding, same as asking an interviewer to confirm. |
| 2026-07-04 | Phase 0 | Tries | LC 208 - Implement Trie (Java) | 37 min (4:56-5:33 PM) | 3/5 | Genuinely unknown territory (no prior Trie exposure) but structure came together correctly with zero conceptual stumbles — all friction was Java-mechanics (variable shadowing between param and field, no default params in Java, array-length vs string-length confusion). Different flavor of gap than DP: this is language-idiom rust, not DSA-concept rust. Code review flagged: startsWith over-engineered (doesn't need the extra search() call or child-check loop), and zero-arg overloads duplicated logic instead of delegating to the charIdx version (root cause of the confusing this.word bug). Self-diagnosed root causes well: added unnecessary `word` field from guessing at an unstated prefix-listing API instead of reading the full method list first; missed `fn(word, 0)` delegation because Lombok's `@Default` normally handles that at work — habit gap, not a knowledge gap. |
| 2026-07-03 | Phase 0 | DP | LC 300 - Longest Increasing Subsequence (Java, O(n²)) | ~60 min active (65 min elapsed − 5 min break) | 2/5 | Recursion (take/skip) came fast (~11 min), but recursion→bottom-up-table translation didn't click on its own — needed a hint on the `dp[i]` = LIS ending at i framing. Independently derived the "patience sorting / tails" dominance-pruning idea from first principles before being taught it — strong signal the underlying DP intuition is intact. Real gap identified: recursive-DP → tabulation translation fluency, not DP concepts themselves. Also flagged: comfort with `int[]` vs `List<Integer>` needs reps — reached for List by habit. |

## Stats Summary
*(update periodically, not every session — last synced 2026-07-10)*
- Total problems solved since restart: 11 (Days 1-11, LC300/208/215/684/207/210/238/49/11/15/3)
- Active days so far: 7 of 8 calendar days (2026-07-03 to 07-10; 07-07 was a gap)
- Current streak: 3 days (07-08, 07-09, 07-10 — the earlier 07-03 to 07-06 run of 4 days ended at the 07-07 gap)
- Current phase: Phase 1 — Pattern Reactivation. Arrays & Hashing and Two Pointers confirmed/closed; Sliding Window in progress (1/2 confirms)
- Weakest topic: Dynamic Programming — real unresolved gap (recursion→tabulation translation), confidence 2/5, no reinforcement rep yet (scheduled for later in Phase 1 when the roadmap reaches DP)
- Strongest topics: Union-Find (5/5, no rust at all), Arrays & Hashing (5/5, 4/5 — fast both times), Redundant Connection-style graph work generally solid
- Recurring pattern to watch: Java collection API mixups (poll/peek, contains/isPresent) and "adjacency list" vs "adjacency matrix" terminology — see C++ → Java Quick Reference section above

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

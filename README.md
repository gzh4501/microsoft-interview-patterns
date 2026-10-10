# Microsoft coding interview questions: the patterns behind the problems that keep showing up, and a prep plan that fits in six weeks

Most people searching for Microsoft coding interview questions are in one of two situations. Either a recruiter just sent a HackerRank link and the assessment closes in five days, or the onsite loop is on the calendar and the prep window is measured in weeks. Both cases have the same practical problem: the internet hands you a list of 50 problems with no explanation of why those 50, and no way to know whether the list is three months old or three years old.

What follows is what the recent public record actually shows about Microsoft's rounds, which problems keep resurfacing, and how to structure the weeks you have.

## The Microsoft loop, as candidates describe it

Microsoft doesn't run one interview. It runs a filter, then a loop.

The filter is usually an online assessment. Candidates who posted experiences through late 2025 and into 2026 describe a HackerRank assessment with two coding problems, hidden test cases, and a hard requirement that the code runs clean against all of them — not a partial-credit situation. One August 2026 write-up described exactly that format: pass the two problems, move to the virtual onsite.

The loop itself is typically three rounds for mid-level candidates. A recent experience report from someone with 3+ years of experience described the split as background and past work, then DSA with object-oriented design, then system design. Three coding problems in a single one-hour round is normal, not an outlier.

Worth noting: the questions in that DSA round were recognizable. Maximum consecutive ones with up to K flips maps to LeetCode 1004. "Minimum time to burn a binary tree" given parent pointers maps to 2385. A message-filtering problem with a K-second window maps to the logic behind Logger Rate Limiter (359). Different wrappers, same underlying problems.

The behavioral portion is short and predictable. Resume walkthrough, the most interesting project you've built, a challenge you hit and how you got past it, your top three learnings, why you picked a particular framework, what you'd do differently if you rebuilt it. That last one is the most useful question to prepare, because it's the one people fumble.

## The problems that keep recurring

Across recent consolidated lists and discussion threads, the question pool clusters into a surprisingly small number of groups. This isn't the full set — Microsoft rotates problems — but it's the shape of it.

| Pattern | Representative problems seen in Microsoft rounds |
| --- | --- |
| Sliding window / two pointers | Max Consecutive Ones III; Longest Substring Without Repeating Characters; substring frequency queries with a distinct-character limit |
| Hashing and strings | Group Anagrams; Integer to English Words; Restore IP Addresses; longest semi-alternating substring |
| Tree BFS/DFS | Amount of Time for a Binary Tree to Be Infected; zigzag level-order traversal; recover a tree from preorder traversal |
| Graph search | Word Ladder and Word Ladder II; Bus Routes; Cheapest Flights Within K Stops; Open the Lock |
| Heaps and top-K | Find Median from a Data Stream; Maximum Frequency Stack; binary-search-on-answer problems framed as server selection |
| Dynamic programming | Word Break; regular expression matching; grid path sums |
| Linked lists | Detect a cycle, measure its length, then break it — all three in sequence |
| In-place array manipulation | Remove Duplicates from Sorted Array; even values on even indices via swaps |
| Greedy and scheduling | Task Scheduler with cooldown; min-strokes fence painting |
| Trie | Prefix search, offline dictionary design, Word Search II |

Two observations from reading these together. First, the difficulty skews medium. Hard problems appear, but they're less common than solid medium problems with a twist. Second, and more important: the wrapper changes constantly while the pattern doesn't.

## The category most question lists skip

Microsoft's online assessments lean heavily on a category that platform-specific lists usually under-serve: ad-hoc simulation. These are problems where the challenge is translating a written business scenario into correct code, not selecting a known algorithm.

From Microsoft OA threads on AlgoMonster's own discussion board and public assessment reports, this category includes things like:

- Turnstile problems — simulating entry/exit timing with a cooldown between uses
- Throttling Gateway — request throttling against a per-second limit
- Minimum moves to obtain a string without three identical consecutive letters
- Concatenated string length with unique characters
- "Largest K such that both K and -K exist in an array"
- Max network rank
- A server-selection problem requiring you to pick exactly k non-adjacent servers while minimizing the maximum value chosen

These reward careful reading and edge-case handling far more than algorithmic cleverness. If you only drill sliding window and DP, you can still lose the assessment on a problem that has no algorithm in it at all.

## Design rounds: they ask for running code

If you're interviewing above entry level, the design portion is where candidates get separated. Candidates consistently report that Microsoft's low-level design rounds want working, threaded, tested code — not a class diagram drawn in the air.

Low-level design topics that have come up recently:

- LRU cache with a time-to-live
- An in-memory key-value store with expiration
- A rate limiter, implemented for real
- A message queue with focus on multithreading and design patterns
- A filesystem design
- Snake game with discussion of which patterns and data structures fit
- A distributed key-value store, and a distributed cache
- Unit tests for a topological sort, including cycle handling

High-level design has been similarly practical: URL shortener (with real discussion of Base62 vs Base64 vs SHA1, redirection flow, and load-balancer counts), Twitter feed with the celebrity-post edge case, a WhatsApp-style chat covering durability and message ordering, a star rating system, a garbage collector.

There's also a layer of system fundamentals that shows up as plain questions rather than a design round: SOLID principles, why dependency inversion is useful, how authentication works in a cloud login flow, microservices versus monolith for debuggability, and how you'd correlate request IDs across services during a debug session.

## Why a 50-question list doesn't get you through

The lists are useful for calibration. They're weak as a primary study method, for one structural reason: Microsoft rotates its problems, and the specific problems you'll see in three weeks aren't the ones on any current blog post. What transfers is pattern recognition — the ability to look at an unfamiliar problem statement and know which family it belongs to within about 90 seconds.

That's also what interviewers are grading. AlgoMonster's published rubric for its mock interviews weights problem-solving and algorithm selection at roughly 35–40% of the score, code understanding and quality at 25–30%, verification and debugging at 15–20%, and communication at 15–20%. That weighting came from hiring-manager feedback. Read it as a rough picture of where the points live: identifying the right approach and explaining it outranks typing a perfect solution.

## How a pattern-first platform fits into this

AlgoMonster is a technical interview prep platform built around that idea — it was created by ex-Google engineers and competitive programmers, and the curriculum is organized as 48 coding patterns rather than as a problem bank. Its stated contents are 500+ lessons across six courses, 1,000+ illustrations, and 3,000+ editorials, with real questions from top tech companies refreshed monthly.

For Microsoft specifically, three parts matter more than the rest:

**The company-specific OA section.** AlgoMonster's forum carries a Microsoft OA category with the simulation problems listed above. If your assessment is five days out, that's the highest-value corner of the platform.

**The decision flowchart.** It walks you through questions — is the input sorted, are you looking for a contiguous subarray, is this a tree or a graph — and lands on the algorithm family you probably need. It's designed as a reference to use while practicing, not something to memorize.

**The inline IDE with the AI assistant.** You can read a pattern and immediately write code against it in the same page, and the AI can explain a passage you're stuck on or help debug. There's also a free AI coding interview hub that breaks down how individual companies structure AI-assisted rounds, including Microsoft's, with a rubric and mock mode.

The format has a real limitation: it's text and diagrams, with no video walkthroughs. If you learn by watching someone solve problems on screen, this will feel like work. AlgoMonster's own FAQ argues video is worse for algorithms because it's less interactive and harder to skim back through — you can decide whether that argument describes you.

Other honest limits: roughly 231 problems means you will not get volume practice here, and the system design material is introductory, so senior-level design loops need something else alongside it. There's also no mentorship or live coaching, and no monthly billing option.

## AlgoMonster pricing

The platform has a free tier and two paid tiers. Prices move with promotions — the subscribe page has listed the yearly plan at $99/year under a 50% discount against a $198 list price, and the lifetime plan at $189 against $378, with lower figures appearing during steeper sales. Checkout is the only number that counts on the day you buy.

| Plan | What you get | Price | Billing | Buy |
| --- | --- | --- | --- | --- |
| Free | Limited access to a subset of patterns and problems — enough to test the teaching style, not enough to prep seriously | $0 | — | [Start with the free tier](https://algo.monster?fpr=li69) |
| Pro — Yearly | All 48 patterns, 500+ lessons across 6 courses, 1,000+ illustrations, 3,000+ editorials, unlimited AI assistant, unlimited Speedrun, company questions updated monthly, member discount on live bootcamps, 12 months of full access | $99/year ($8.25/mo billed annually; list $198) | Annual, cancel or upgrade anytime | [Get the yearly plan](https://algo.monster?fpr=li69) |
| Pro — Lifetime | Everything in the annual plan plus lifetime updates, paid once, yours permanently | $189 one-time (list $378) | One-time | [Get lifetime access](https://algo.monster?fpr=li69) |

Both paid tiers also include the Foundation course and a "Build an LLM" course at no additional cost, and subscribers get future courses as they're released.

Three things worth knowing before you pay. There's no monthly plan, so this is either an annual or a one-time commitment. The yearly plan works out to roughly 27 cents a day at the current promotional price. And the listed strike-through prices mean the discount is the normal state, not a rare event — so there's no reason to panic-buy on the last day of a sale.

## Which plan actually fits your situation

If your onsite is in the next month or two, the yearly plan is the obvious pick. You get everything the lifetime plan gives you for the duration that matters, at about half the upfront cost, and you're not buying access to content you'll revisit in four years.

The lifetime plan makes sense in a specific case: you expect to interview at least twice more over the next five to seven years. Engineers who move every two or three years and re-prep each time are the audience for it. If you're doing one focused job search and then settling in for a while, $189 for a few weeks of study is real money.

As for the free tier — it's a genuine preview, but it isn't prep. Use it to check whether the text-and-diagram format clicks with how you learn, then decide.

## A six-week structure that maps to how Microsoft tests

This is a plan, not a promise. Adjust it to the time you actually have.

**Weeks 1–2: patterns, not problems.** Work through the core families — two pointers, sliding window, hashing, binary search, trees, graphs, heaps. Write the code yourself in the inline editor instead of reading the solution and nodding. The goal is recognizing the family, not memorizing templates.

**Week 3: drill the recurring Microsoft problems.** Take the table above and work each entry to a clean, tested solution. Group Anagrams, Word Ladder, Amazon-style nothing — just the actual list. Word Ladder II in particular is worth the time; it shows up repeatedly.

**Week 4: ad-hoc simulation.** This is the week most candidates skip and then pay for. Go through the Microsoft OA problems — turnstile, throttling, three-consecutive-letters, semi-alternating substrings. Practice reading a novel scenario and writing correct code without reaching for an algorithm.

**Week 5: design.** Implement LRU with TTL and a rate limiter from scratch, with tests. Then sketch the URL shortener and the Twitter feed out loud. Cover durability and ordering for the chat design.

**Week 6: timed runs and behavioral.** Use Speedrun mode to practice under a clock. Write out your project answers — the challenge, the top three learnings, what you'd rebuild differently — because those questions are near-guaranteed and unrehearsed answers sound unrehearsed.

Throughout, use the flowchart when you're stuck on categorization, and check that your solutions actually pass tests. The rubric weighting suggests that verifying your own code is worth as much as writing it.

## The short version

Microsoft's question pool is broad but shallow in terms of distinct ideas. Maybe ten pattern families cover the large majority of what candidates report seeing, plus a simulation category that generic lists under-serve and a design round that expects working code. A list of 50 questions gets you calibrated for a week. A pattern-first approach gets you through an unfamiliar problem in a round you didn't prepare for, which is the situation you'll actually be in.

If you want to see the current promotional price and how the curriculum is organized, 👉 [take a look at AlgoMonster's plans here](https://algo.monster?fpr=li69) — and if you're still deciding, the free tier will tell you inside an hour whether the format suits you.

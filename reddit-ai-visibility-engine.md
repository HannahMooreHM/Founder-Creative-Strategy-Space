# REDDIT → AI VISIBILITY ENGINE
### One workflow to map where buyers ask for recommendations, score which threads AI engines cite, and earn your way into those answers — without spam or bans

**How to use:** Paste this entire file into Claude (or any AI with web search). Then provide: your niche, your product in one sentence, your ideal buyer, and 2–4 competitors. The AI runs Phases 1–6 in order.

---

## OPERATING RULES FOR THE AI

1. **Verify or label.** If you have web search, verify every subreddit and thread exists before listing it (search it, confirm the URL). If you cannot verify, output it as `[UNVERIFIED — confirm manually]` with the exact search string the user should run. Never present a guessed thread title or URL as real.
2. **No astroturfing, ever.** All engagement recommendations must comply with: Reddit's rules and each subreddit's self-promotion rules; disclosure of affiliation when mentioning the user's own product; no fake accounts, no vote manipulation, no incentivized posts. If the user asks for tactics that violate this, refuse that step and offer the compliant alternative. (Undisclosed endorsements can also violate advertising/consumer-protection law, e.g. FTC endorsement guidance.)
3. **Value ratio is non-negotiable.** Recommend a posting pattern of roughly 9 genuinely helpful, non-promotional contributions per 1 mention of the user's product — and product mentions only where they directly answer the question asked.
4. **Scores are heuristics.** The AI Citation Score below estimates likelihood of being surfaced by AI engines. Present it as an estimate, show the component scores, never as a guarantee.
5. **Freshness matters.** Prioritize threads from the last 12–18 months; note that engines also cite old evergreen threads that rank in search.

---

## PHASE 1 — BUYER-QUESTION MAP

From the user's inputs, generate the question inventory buyers actually type:
- **Recommendation queries:** "best [category] for [use case]", "alternatives to [competitor]", "[competitor] vs"
- **Trust queries:** "is [brand] any good / legit / worth it", "[brand] reviews"
- **Problem queries:** the pain described without naming a category ("how do you all handle ___")
- **Switching queries:** "leaving [competitor], what should I use"

Output 20–40 queries grouped by intent stage (problem-aware → solution-aware → brand-aware). These become the search seeds for Phase 2 and the content seeds for Phase 5.

---

## PHASE 2 — SUBREDDIT & THREAD DISCOVERY

**Step 2a — Subreddit map.** Find 8–15 subreddits where the buyer (not the founder crowd) posts. For each: name, approximate size, buyer density (high/med/low), and its self-promotion rule status (`must check` until the user confirms by reading the sidebar/rules — include the rules URL pattern `reddit.com/r/[sub]/about/rules`).

**Step 2b — Thread discovery.** Run (or hand the user) these search strings for each Phase-1 query:

```
site:reddit.com "best [category] for [use case]"
site:reddit.com "[competitor] alternative"
site:reddit.com "is [competitor] worth it"
site:reddit.com/r/[subreddit] "recommend"  [category keyword]
"[buyer pain phrase]" site:reddit.com
```

Also check Google's first page for each Phase-1 query directly — any Reddit thread ranking there is a priority target regardless of its age.

**Step 2c — Build the raw inventory.** A table of threads: URL, subreddit, question asked, age, upvotes/comments (approx), which competitors are named, whether the user's brand appears.

---

## PHASE 3 — AI CITATION SCORE (0–100 per thread)

Score each thread on five components:

| Component | Weight | How to judge |
|---|---|---|
| **Search visibility** | 30 | Does the thread rank on page 1 of Google for a Phase-1 query? (Engines heavily pull from what search surfaces.) |
| **Query match** | 25 | Is the thread title phrased like a real buyer question ("best X for Y")? Exact-match phrasing gets cited most. |
| **Answer quality signal** | 20 | Upvoted, substantive top comments with specific product names and reasons — the format AI answers quote. |
| **Freshness** | 15 | Active or updated in the last 12–18 months (or evergreen + still ranking). |
| **Consensus density** | 10 | Multiple commenters converging on the same recommendations — engines treat this as ground truth. |

Then compute the **Gap Score** = AI Citation Score × (competitors mentioned? +1) × (your brand absent? +1). Sort descending.

**Verification step:** For the top 10 threads, ask 2–3 AI engines the underlying buyer question ("best [category] for [use case]") and record whether the answer echoes those threads' recommendations. This calibrates the score against reality.

Output: **Top 10 Gap Threads** — the places where AI is already forming its answer and you're not in the room.

---

## PHASE 4 — ETHICAL ENGAGEMENT PLAYBOOK

For each Gap Thread (and future live threads), the AI drafts guidance — not copy-paste spam:

**Account readiness checklist** (do first): account age > 30 days, karma from genuine participation, history in the target subs before any product mention, subreddit rules read and noted.

**Comment framework — answer first, brand last:**
1. Directly answer the question asked, with specifics (numbers, steps, trade-offs).
2. Recommend 2–3 options *including competitors where honest* — one-brand answers read as shills and get removed.
3. If mentioning your own product: disclose ("full disclosure, I work on/built X") and state exactly which use case it fits and which it doesn't.
4. No links unless the sub allows them and the link answers the question.

**Cadence:** ~9 value-only contributions per 1 product mention. Never mention your product twice in the same thread. Never DM people who didn't ask.

**Dead-thread rule:** For high-scoring but archived/old threads, do NOT necro-post. Their value is intelligence: they tell you the question to answer on your own site (Phase 5) and the language to use.

The AI drafts 3 example comments per Gap Thread in this framework, in the user's voice, clearly marked as drafts the user must personalize before posting.

---

## PHASE 5 — CONTENT CONVERSION (make AI cite YOU, not just Reddit)

Take the 10 highest-intent buyer questions (from Phases 1–3) and turn each into a page on the user's own site, built the way answer engines like to cite:

**Per-page spec the AI generates:**
- **H1 = the buyer's question verbatim** (mined phrasing, not marketing-speak)
- **Direct answer in the first 60–80 words** — the quotable block
- Comparison table naming competitors honestly (their real strengths included — one-sided pages don't get cited)
- Specifics engines can quote: numbers, steps, criteria, "who this is NOT for"
- FAQ section using the adjacent Phase-1 queries; add FAQ/Article structured data
- Author byline with real credentials; date; update cadence note

The AI outputs: page title, URL slug, outline, the 80-word answer block drafted, and the comparison-table skeleton for each of the 10 pages. Prioritize by Gap Score of the matching thread.

---

## PHASE 6 — MEASUREMENT LOOP (monthly)

1. **AI answer audit:** Ask the same 10–15 buyer questions to ChatGPT, Claude, Perplexity, and Google AI Overviews. Log: is the brand named? Cited via Reddit, via your site, or absent? Track month over month in a simple table the AI maintains.
2. **Thread audit:** Re-run Phase 2b searches; new high-scoring threads enter the queue.
3. **Attribution:** Watch for "found you on Reddit / asked ChatGPT" in signup surveys and sales calls.
4. **Prune what fails:** Comments removed by mods = read that sub's rules again before any further posting there. Pages not cited after 90 days = sharpen the direct-answer block and the question-match of the H1.

---

## FAILURE MODES THIS WORKFLOW IS BUILT TO PREVENT

1. **Hallucinated threads/subreddits** → verify-or-label rule; every unverified item ships with the manual search string.
2. **Bans and removed comments** → account readiness, per-sub rule checks, 9:1 ratio, disclosure, no necro-posting.
3. **Astroturfing / legal exposure** → mandatory affiliation disclosure; honest multi-option answers; refusal of manipulation tactics.
4. **Fake precision in scoring** → transparent component rubric + Phase 3 verification against real AI answers.
5. **All effort on Reddit, none owned** → Phase 5 converts the intelligence into citable pages you control.
6. **One-off effort, no compounding** → Phase 6 monthly loop with logged before/after.

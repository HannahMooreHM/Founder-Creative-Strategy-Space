# [CLIENT NAME] — Brand Strategy & Requirements v4
*Strategy before pixels. Worked through five lenses:*

## HOW TO READ THIS DOCUMENT — the legend

**Every section follows the same anatomy**, so you always know where you are:

| Part | What it looks like | What it's for |
|---|---|---|
| **Purpose line** | *Italic sentence under the heading* | One sentence: what this section does and why it exists |
| **In one line** | Bold summary box directly under the heading | The conclusion first (Minto style) — reading only these boxes gives the whole strategy in under a minute |
| **The work** | Tables and `[BRACKETS]` to fill | The actual strategy content |
| 💡 **Plain English** | Quote box | The same idea, explained simply, usually with an analogy |
| 🎓 **Teaching moment** | Quote box with a name | The thinker behind the idea, and the one lesson to steal from them |
| ✍️ **Client answer box** | Dashed box with a blank line | Something only the client can answer: the question, a space to write, then *(in grey)* why we ask and what we'll do with the answer |
| ✅ **To-do** | Checklist | What must be done before this section is "closed" |

**Reading by colour** (in the HTML version): dark panel = a decision was made · white bordered card = evidence & options · soft band = rules & requirements · dashed box = the client owes an answer.

**Stacked numbering rule** — every numbered sequence renders as a vertical list, 1 above 2 above 3. Never an inline run ("1 · x 2 · y"): if the order matters enough to number, it matters enough to stack.

**Lens badges** — small tags like `NEUMEIER` `RIES` `GALLOWAY` mark whose method a rule comes from. When two ideas conflict, the badge tells you which book to reopen.

**Experiment status pills** — every experiment in §6 and Appendix A carries exactly one status:
📝 `DRAFT` (designed, not launched) → 🟢 `LIVE` (running, don't peek) → 🔍 `READ` (results in, decision pending) → 📒 `LOGGED` (learning written to the ledger — only now is it finished).

**`[SQUARE BRACKETS]`** — either resolve them or carry them to the open-questions list. A bracket left silently unfilled is a defect.

**The comprehension gate** — every Plain-English box, answer box, and instruction must pass the 15-year-old test: *would a smart 15-year-old understand this AND know what action is required?* If not, rewrite it before shipping.

---

## 0 · Output format & document styling — READ FIRST
*Purpose: the document itself must look like the brand it describes — proof the method works before a single website pixel exists.*

**The deliverable is a styled, single-page HTML document** (plus this markdown source).

### 0.1 · Palette derivation (inputs: client logo → website → social media, in that priority order)
1. Pull the 2–4 main colours from the **logo** (sample the actual file; never guess).
2. Cross-check the **live website and social profiles** — where the brand contradicts itself, that's a finding; log it in §3.
3. Turn the palette into a **strict usage system**: every colour gets exactly ONE job. Fill this table:

| Role | Hex | Rule |
|---|---|---|
| Canvas | `[#______]` | evidence over decoration — generous whitespace |
| Ink / dark panels | `[#______]` | body text + "a decision was made here" panels |
| **Single action colour** | `[#______]` | if it's [colour], it's clickable — nothing else may be |
| Warmth cue | `[#______]` | pills and soft info bands only |
| Accent / stats | `[#______]` | stars, numbers, labels on dark panels only |
| **USP colour** | `[#______]` | reserved *only* for the brand feature customers name unprompted (§2) |
| Secondary text / hairlines | `[#______]` / `[#______]` | muted greys, 1px borders |

> **Worked example (a Dubai nursery):** White `#FFFFFF` canvas · deep navy `#13242F` text/panels · blue `#2E5FD7` as the only clickable colour · pale butter `#FBF3D3`/`#FDF8E1` warmth bands · butter-gold `#EFC53F` stars & stats · green `#2F8C5C` for their garden programme · red `#C8392B` reserved solely for their famous red front door.

### 0.2 · Typography & hierarchy (adapt to the client's register)
- One characterful display face (600–800 weight) for headings — *e.g. Bricolage Grotesque*; one warm, easy-to-read body face at 14–15px with 1.6–1.8 line-height — *e.g. Nunito Sans*; at most one handwritten flourish, for the tagline only — *e.g. Caveat*.
- Small-caps eyebrow labels: 12px, 800 weight, .1–.14em letter-spacing, uppercase.
- Single 920px centred column; 40–56px padding; H1 34px → H2 26px → H3 17–20px → body 14–15px.

### 0.3 · Semantic panel system (colour-coding, not decoration)
- **Dark ink panels** = decisions made · **white bordered cards** (1px hairline, borders not shadows) = evidence & options · **warmth bands** = rules & requirements.
- Colour-coded pill tags (uppercase, 999px radius) label every card at a glance; each card scans in three beats: *tag → finding → what we do about it*.
- Rounded corners (16–20px), flat print-like calm, no imagery — text is the artifact; manage density with grid gaps, not divider lines.
- Inline emphasis via coloured `<strong>` keyed to the section or ICP colour.

### 0.4 · The plain-language & interaction layer *(added in v4 — applies to every section)*
1. **Minto first.** Directly under every section heading (after the purpose line), write one bold **"In one line:"** sentence stating the section's conclusion. A reader skimming only these boxes must come away with the whole strategy. If you can't write the one-liner, the section isn't finished.
2. **The 15-year-old test.** Every Plain-English box, instruction, and answer box must be understandable — *and actionable* — by a smart 15-year-old. Prefer the plain name in body copy, keep the formal name in headings for cross-referencing: review-mining corpus → **the quote bank** · register rules → **voice rules** · riskiest assumption → **the scariest belief** · decision metric → **scored by** · threshold → **pass-mark** · iterate → **tweak** · pivot → **rethink**. Experiment IDs (`E-HERO-01`), status pills, and ledger IDs stay technical — they are the tracking system's plumbing — but each is defined in plain words on first use.
3. **Stacked numbering.** All enumerations render vertically, 1 above 2 above 3. In the HTML, style numbers as small chips; in markdown, use real ordered lists. Never compress a numbered sequence into an inline run.
4. **✍️ Client answer boxes.** Every input only the client can supply becomes a dashed answer box, placed in the section that needs it, containing exactly three things:
   1. **The question**, with tick-box options where possible (☐ yes ☐ no ☐ other: ___).
   2. **A visible blank answer line** the client can write on.
   3. **Grey explanatory text**, two clauses, always in this order: *"Why we ask: [what breaks or stalls without it]. What we'll do with it: [the exact section/experiment the answer feeds]."*
   Then **collect every box in one dark panel at the very top of the document**, priority-ordered, each with a one-clause grey reason — so the client can answer everything in a single sitting. The top panel and the in-section boxes must match one-to-one.
5. **Versioning.** Each regeneration bumps the version (v1 → v1.1 → v1.2) and opens with a short "What changed since [previous]" line, so the client never has to diff documents by eye.

> 💡 **In plain English:** we borrow the client's own colours and give each one a single job — like a well-run kitchen where every knife has one purpose. A reader should be able to skim by colour alone: dark panel? a decision. White card? evidence. This trains the client's team in colour discipline before the website exists.

**✅ To-do — Styling**
- [ ] Obtain logo file + live site + 2 social profiles; extract palette
- [ ] Log any brand inconsistencies found across channels
- [ ] Fill the role table; confirm the action colour and USP colour with client
- [ ] Build the HTML shell before writing content into it

---

## 1 · Positioning — the onliness statement `NEUMEIER` `GODIN`
*Purpose: one sentence a competitor cannot copy tomorrow, backed by receipts anyone can check.*

**[CLIENT] is the only [category] in [market] that [defensible combination of facts].**
**The 8-word test:** [onliness in ≤8 words — if it won't compress, it isn't an onliness yet]
**The zag:** competitors scale **[what the whole category scales]**; [CLIENT] scales **[what only they can scale]**.
**The remarkable thing** *(what customers retell at dinner)*: "[specific, concrete, slightly surprising fact]"
**Trust drips** *(5–8 receipts — nouns and numbers, each one checkable — now with the Tomorrow Test)*:

| Receipt | Status | Tomorrow Test: could the market leader say this tomorrow? |
|---|---|---|
| [X years / founder fact] | ☐ verified | [yes — competitors have founders too / no — because ___] |
| [award, year] · [rating, platform] · [checkable policy] | ☐ verified | [___] |
| [customer-recognised brand feature — see §2] | ☐ verified | [___] |

**⭐ The Sleeper Receipt.** After filling the table, rank the receipts by the Tomorrow Test. The receipt the market leader **structurally cannot copy** — because their business model, scale, or incentives forbid it (e.g. a delisting policy an inventory-scaling platform could never announce) — is the *sleeper receipt*. Rules: (1) it must be promoted out of any FAQ or footer into a **named, visible promise** with its own section; (2) it is the second candidate (after §2 value 4) for the reserved USP colour; (3) if two receipts tie, the one phrased as a *policy with consequences* beats the one phrased as an effort.

> 💡 **In plain English:** "onliness" means finishing the sentence *"we're the only ___ that ___"* with facts, the way you'd describe the only bakery in the village that still bakes overnight. The "zag" is simple: when everyone in the category turns right, you turn left. And "trust drips" work like a dripping tap filling a bucket — you never *claim* to be trustworthy; you let small, checkable facts accumulate until the bucket is full.

> 🎓 **Teaching moment — Marty Neumeier:** brands don't compete on better, they compete on *different*. A customer can't rank fifteen "betters", but they can remember one "only". If your onliness statement would also be true of your nearest competitor, you don't have one yet.

**✅ To-do — Positioning**
- [ ] Draft onliness; run the 8-word test
- [ ] Verify every trust drip against a source (screenshot or link it)
- [ ] Confirm the remarkable thing is something a real customer has actually retold

---

## 2 · Review mining — what customers already validate `SCAMAN`
*Purpose: find the marketing your customers have already written for you, word for word.*

*Method: auto-searched corpus (Google reviews, Trustpilot, Reddit, [category review sites], first-person customer blogs) + the client's private evidence. Every value below carries a verbatim quote ≤15 words with platform + date, or is tagged `unvalidated — hypothesis only`. Every validated value must get a visible answer on the site.*

**The table below is a floor, not a ceiling.** Six rows are the minimum; keep adding rows until the corpus is exhausted. The corpus must cover these strata — if any stratum has no quote, that is a research gap to log, not a row to skip:
- **the emotional extreme** (the worst moment customers describe — tears, dread, giving up)
- **the daily tax** (the recurring cost in time/energy, in their words)
- **the category's core failure** (what incumbents get wrong, named)
- **enemy distrust** (the incumbent label/phrase customers have learned to disbelieve)
- **the transformation sought** (what they're really buying — usually not the product noun)
- **the persistent residue** (what still hurts even for veterans/loyal customers)

**Corpus quality line (mandatory):** end this section by stating the corpus's own weakness in one sentence (e.g. "zero first-party quotes — the first ten customer emails outrank everything above; harvest them relentlessly"). Rank sources: first-person customer voice > practitioner/enthusiast blogs > journalists & aggregators > competitor marketing (always tagged).

| # | Proposition value (principle) | Customer's own words | Applied where |
|---|---|---|---|
| 1 | **Rare-in-market differentiator** — customers set it against the whole category | "[quote]" (platform, yr) | headline claim |
| 2 | **The deciding fact** — what settles it for the evidence-driven buyer | "[quote]" | first "Why" card |
| 3 | **Belonging / community value** | "[quote]" | hero + community section |
| 4 | **Customer-recognised brand feature** — a physical or experiential asset customers name *unprompted* | "[quote naming it]" | dedicated promise band + reserved USP colour (§0.1) |
| 5 | **Observable proof of the method** — what an outsider can see with their own eyes | "[quote]" | day-in-the-life / demo |
| 6 | **Buyer-serving value** — serves the payer, not just the end user | "[quote]" | kept high on the page |

> 💡 **In plain English:** review mining is panning for gold in words customers already wrote. Your best headlines exist — they're just sitting in a Trustpilot review from last March. Value #4 is the jackpot: something customers mention without being asked (a famous door, a founder who answers her own phone, a signature ritual). Competitors can't copy it because it grew from customers, not a workshop — so it earns its own reserved colour and its own section. *(Worked example: nursery parents kept mentioning the red front door unprompted — it became a promise band on the site and the only red thing in the whole brand.)*

> 🎓 **Teaching moment — Sarah Scaman:** the audience has already written your best lines. The copywriter's job isn't invention, it's *curation* — and a community that talks about you is a moat no ad budget can buy.

**✅ To-do — Evidence**
- [ ] Run the auto-search across all listed platforms; log quotes with source + date
- [ ] Identify the customer-recognised brand feature (or record that none exists yet)
- [ ] Tag every unproven value `unvalidated`; add to open-questions list
- [ ] Map each validated value to a named site element

---

## 3 · Design system — decision log
*Purpose: record why each design choice was made — including what we rejected — so the choices survive future opinions.*

*Format: what we chose → what it signals → what it opens up. Log rejected options too ("[rejected] read as [signal]; [chosen] reads as [signal]"). The palette itself lives in §0.1 — this section records the reasoning.*

- **[Canvas]** — [signal] · **[Warmth]** — [where allowed] · **[Action colour]** — one job: clickability · **[USP colour]** — reserved for the customer-recognised feature · **[Accent]** — stats and ratings only.
- **Decisions this opens up:** [photography brief] · [feature → logo lockup?] · [live review widget vs curated wall] · [remaining choices].

**Logo semantics ruling (mandatory).** Beyond sampling its colours, rule on what the mark *depicts and signals*: [what is it? what does it say about the category promise? does it survive the gate test — would the customer at the gate moment feel it matches the stakes?]. If the mark's meaning conflicts with the positioning (e.g. a playful mascot on a safety-critical brand), log it as a strategic decision to make deliberately — keep-and-own, evolve, or replace — never leave it unruled.

**Asset Placement Audit (mandatory).** List the client's 3–5 strongest assets (founder story, sleeper receipt, killer policy, best proof), then for each: *where it currently lives → where the buying decision needs it → the move order.* An asset buried in an About page or FAQ accordion is inventory, not marketing. Format:

| Asset | Currently lives | Decision needs it | Move order |
|---|---|---|---|
| [founder story] | [About page, anonymous on homepage] | [hero-adjacent, named, faced] | [___] |
| [sleeper receipt — §1] | [FAQ #n] | [named promise band] | [___] |

> 💡 **In plain English:** a decision log is the brand's immune system. Six months from now someone will say "let's make the buttons [other colour]" — and instead of re-arguing from scratch, you point at the page that says why the buttons are the colour they are, and what the other colour would have signalled.

**✅ To-do — Design**
- [ ] Write one decision-log line per colour role
- [ ] List the 3–5 downstream decisions this opens; assign owners

---

## 4 · Core ICPs (2–4) `GODIN`
*Purpose: name the exact people we serve — not as demographics, but as moments of need.*

*Fixed format, every clause mandatory:* **For [who] → who feels [emotional hook] → [CLIENT] solves [problem in their words] → so they get [value] → without [fears/frictions of the alternative].**

### ICP 1 · [The emotional-primary buyer] `PRIMARY`
For [who — geography, life stage, trigger], who feel [the ache/guilt/fear, named precisely], [CLIENT] solves the "[their inner question]" problem — [receipt], [receipt] — so they get [transformation for the end user] **plus [transformation for the buyer themselves]**, without [competitor failure], [category sin], or [the private doubt they'd never say aloud].

### ICP 2 · [The evidence-driven, time-poor buyer]
For [who — a situation forcing a fast decision], who feel [decision fatigue / fear of an expensive mistake], [CLIENT] solves the **evidence problem** — [verifiable receipts] — so they get [a confident yes after one interaction] and [direct access to the accountable person], without [salesy funnels], [hidden costs], or [layers between them and accountability].

### ICP 3 · [The bridge into a second offering] `bridge`
For [who — often an existing customer] ready to [transformation], who feel [invisibility/uncertainty], [SECOND OFFERING] solves [the barrier] — [receipt borrowing the core brand's credibility] — so they get [credential/outcome] and [a path back into the ecosystem], without [quitting X], [generic alternative], or [starting from zero].

> 💡 **In plain English:** an ICP isn't a demographic, it's a *moment* — a specific person, feeling a specific ache, asking a specific inner question. Think of it like prescribing medicine: you don't prescribe for "adults aged 30–45", you prescribe for *this symptom, presenting now*. ICP 1 buys on feeling (remove the guilt, never mention it). ICP 2 buys on receipts and speed. ICP 3 turns customers into your talent or advocate pipeline. Every experiment in §6 declares which ICP it targets, because a line that wins for one can lose for another.

> 🎓 **Teaching moment — Seth Godin:** find the smallest market that can sustain you and serve it so well they'd miss you if you were gone. "Everyone" is not a market; it's a way of hiding from the choice.

**✅ To-do — ICPs**
- [ ] Complete every clause for each ICP; no clause skipped
- [ ] Source each "emotional hook" from a real quote or call note
- [ ] Confirm with the client which ICP is primary (it drives the default homepage)

---

## 5 · Register rules — every line, every channel `SCAMAN`
*Purpose: fix the vocabulary. The customer's dialect goes in; the company's internal jargon stays out.*

1. **Never the distancing plural** ("them/kids/users") — always "your [___]", singular and warm. *(Segment language may survive on B2B/mission pages, where it belongs — never in the customer's moment.)*
2. **Their words, not our KPIs** — they say *[mined vocabulary]*; only we say *[banned internal words: trust, convert, book, engage]*. **Comfort-language exception:** technical terms that customers themselves use verbatim (medical, safety, craft vocabulary — check the §2 corpus) are *comfort language* — precision reads as care; keep them. The jargon ban applies to **company-side** language only: product-manager phrasing, KPI words, feature-speak the customer has never uttered.
3. **Proof lives in nouns and numbers**, never adjectives.
4. **The gate test:** if no customer would say the line aloud at the gate moment, cut it. **The gate moment must be an evidenced venue, not an imagined scene** — name the real place the decision happens (a named forum, a Facebook group, a kitchen-table conversation, a school-run chat) and cite the evidence from §2 or intake that puts the decision there. A cinematic scene the strategist invented is a hypothesis; tag it as one.

> 💡 **In plain English:** "register" just means speaking the customer's dialect — like a local, not a tourist with a phrasebook. The most common failure is rule 2: your internal goals ("book now!", "trust us") leaking into their moment. Rule 4 is the cheapest quality check in marketing — read the line aloud as if to the customer's face. If you'd cringe, cut it.

**✅ To-do — Copy rules**
- [ ] Extract 8–12 mined vocabulary words from the review corpus
- [ ] List the banned internal words
- [ ] Define the client's "gate moment" for the gate test

---

## 6 · THE EXPERIMENT ENGINE `RIES` `MAURYA`
*Purpose: turn opinions about copy into knowledge about customers — one cheap, honest test at a time.*

### 6.0 · The loop — how every experiment lives and dies `RIES`

Every experiment travels the same circuit, and the status pill tells you where it is:

**📝 DRAFT** (card written, prediction committed) → **🟢 LIVE** (running; no peeking before the read date) → **🔍 READ** (results in; decide: ship / iterate / kill) → **📒 LOGGED** (learning written to the ledger). *An experiment without a ledger entry never happened.*

This is Build–Measure–Learn in brand clothing: the card is the plan, the live test is the build, the decision metric is the measure, and the ledger entry is the learn. **The unit of progress is validated learning — not traffic, not likes, not applause.**

> 🎓 **Teaching moment — Eric Ries:** beware *vanity metrics* — numbers that go up and make you feel good but decide nothing (impressions, followers, page views). Applause is not the same as buying. Every experiment here names ONE decision metric in advance, so the result can't be spun after the fact.

### 6.1 · Order of attack — riskiest assumption first `MAURYA`

Before writing any experiment, list the beliefs the whole strategy leans on, then rank them by: **if this is wrong, how much collapses?** Test the top one first.

| # | Assumption the strategy leans on | If wrong, what collapses? | Tested by |
|---|---|---|---|
| 1 | [e.g. ICP 1 buys on guilt-removal, not features] | the hero, the emails, the page order | `E-____-01` |
| 2 | [e.g. the brand feature (§2, value 4) actually drives decisions] | the USP colour, the promise band | `E-____-02` |
| 3 | [assumption] | [what collapses] | `E-____-03` |

> 💡 **In plain English:** your strategy is a Jenga tower and some blocks are near the bottom. Test the bottom blocks first — it's cheaper to learn the tower falls over *before* you've built the website, the email sequence, and the ad campaign on top of it.

> 🎓 **Teaching moment — Ash Maurya:** "Life's too short to build something nobody wants." Fall in love with the customer's *problem*, not with your solution — and spend your first experiments attacking the assumption most likely to kill you, not the one easiest to test.

### 6.2 · The experiment card — fixed schema, no exceptions

| Field | Rule |
|---|---|
| **ID** | `E-[channel]-[n]` (E-HERO-01, E-SUBJ-01, E-SOC-01, E-FEES-01) |
| **Status** | 📝 DRAFT / 🟢 LIVE / 🔍 READ / 📒 LOGGED — exactly one |
| **ICP** | one, singular |
| **Builds on** | ledger entry ID(s) — or `L0 (cold start)` |
| **Assumption attacked** | which row of the 6.1 table this tests |
| **Variable isolated** | ONE thing changed; everything else held constant |
| **Hypothesis** | "If [change], then [metric] moves, because [ICP insight]" |
| **Cells** | A (control = incumbent line) / B / C |
| **Decision metric** | ONE metric + threshold + minimum sample/duration — vanity metrics banned |
| **Read date** | fixed *before* launch — no peeking, no early calls |
| **Expected winner** | committed before running — being wrong is the valuable outcome |
| **Learning written** | the ledger sentence this will produce, whichever cell wins |

> 💡 **In plain English:** most teams run tests; almost nobody runs *sequences*. "Builds on" forces each test to stand on the last one's shoulders — a staircase, not a pile of bricks. "Expected winner" forces a falsifiable prediction about your customer: when you're wrong, you've learned something real. Ten tests run this way don't give you ten winning lines; they give you a *theory of your customer* that writes winning lines on demand.

### 6.3 · Challenge the client's own lines first (≥4, and the live H1 + hero subhead are always among them)
Every challenge must apply **both named tests** and show the verdict of each:
- **The Tomorrow Test** `NEUMEIER`: could the market leader run this exact line tomorrow without changing anything about their business? If yes, it's a category label, not a position.
- **The gate test** `SCAMAN` (§5.4): would the customer say it aloud at the evidenced gate venue?

**"[Live H1]"** — Tomorrow Test: [verdict + why]. Gate test: [verdict]. [Diagnosis: what it opens on, whose language, what it demotes]. Survives only as the control cell — we expect it to lose.
**"[Live hero subhead]"** — [right insight / wrong register? which internal phrasing is leaking?]. Their actual inner line, verbatim from the evidence: "[mined quote]". Rewritten: **"[customer-register version]"**.
**"[Existing line 3]"** — [which internal KPI is leaking into the customer's moment]. Rewritten: **"[___]"**.
**"[Existing line 4]"** — [adjective without a receipt / hedge-word the audience has been burned by]. Rewritten: **"[___]"** *(prefer direct lifts from the founder story or the mined corpus — the best copy usually already exists on the property, hidden).*

### 6.4 · Hero H1 lab — one card per ICP
`E-HERO-01 · 📝 DRAFT · ICP 1 · Builds on: L0 · Decide by: [primary CTA action]`
A "[incumbent]" *(control)* · B "[same insight, guilt/friction removed]" — isolates the frame · C "[specific retellable proof fact]" — tests feeling vs proof. **Expected winner:** [_] because [ICP insight].
`E-HERO-02 · 📝 DRAFT · ICP 2 · Decide by: time-to-first-CTA` — A control · B "[Receipt. Receipt. Receipt.]" (proof-density vs poetry) · C "[the decision-speed promise itself]" (relief from comparison fatigue).
`E-HERO-03 · 📝 DRAFT · ICP 3 · Decide by: [section] scroll depth · [offering] CTR` — A control · B "[near-verbatim review line]" (the audience writes better headlines than we do) · C "[onliness led from the buyer's own transformation]" (if C wins, that value moves up the hierarchy).

### 6.5 · Email subject-line lab — the cheap laboratory `RIES`
*Decide by open rate (the subject's only job) — but log clicks too, so a curiosity subject that wins opens and loses clicks gets caught.*
`E-SUBJ-01 · 📝 DRAFT · ICP 1 · Builds on: E-HERO-01` — A "[generic company update]" *(control)* · B "[specific proof as subject, personalised]" · C "[open loop built from the ICP's named ache]". **Expected:** C for opens, B for clicks — which is itself the learning.
`E-SUBJ-02 · 📝 DRAFT · ICP 2 · Builds on: E-HERO-02` — A "[KPI language in their inbox]" · B "[number-led receipt]" · C "[time-relief promise]".

> 💡 **In plain English:** email is your wind tunnel; the website is the aircraft. A subject-line test resolves in 48 hours on your existing list, while a homepage test needs weeks of traffic — so run the *frame contest* (feeling vs proof vs curiosity) in the wind tunnel first, then build the winning frame into the expensive channels. This is the minimum viable test: the smallest, cheapest version that still teaches you something true. The register rules still apply — a subject that wouldn't survive the gate test will win opens and poison trust.

### 6.6 · Social & video lab `GALLOWAY` `MAMMERI`
*Decide by hold rate / "read more" expansion → then profile taps. The first line's only job is to earn the second line.*

**Rule 1 — Packaging first `GALLOWAY`.** Decide the hook, title, and thumbnail (or opening frame) *before* making the content. If the packaging can't be made compelling, the idea isn't worth producing — kill it at the idea stage, not in the edit.
**Rule 2 — Study the outliers `GALLOWAY`.** Keep an **outlier file**: posts in your category that massively outperformed that account's normal numbers. Outliers reveal what the *audience* rewards; averages only reveal habits. Every `E-SOC` card should cite at least one outlier it's learning from.
**Rule 3 — The hook is the whole game `MAMMERI`.** If they skip the hook, they skip the rest — so most of the writing effort goes into the first line/three seconds. But no clickbait and no cringe: the hook must be paid off, because a welched promise burns the exact trust your positioning banks on.
**Rule 4 — One post, one idea.** Two ideas in one post means the viewer holds neither.
**Rule 5 — Format before volume `MAMMERI`.** Don't post randomly and hope. Design one **repeatable weekly format** (same structure, new content each week), run it as its own experiment (`E-FMT-01`), and only add a second format once the first is read and logged. Systems beat one-off virality.

`E-SOC-01 · 📝 DRAFT · ICP 1 · Builds on: E-SUBJ-01 · Outlier cited: [link/description]` — A "[We're proud to announce…]" *(control)* · B "[confession/tension hook — a specific human moment, brand as setting not subject]" · C "[contrarian category truth — names the enemy, positions the zag as a belief]".
`E-SOC-02 · 📝 DRAFT · ICP 3 · Builds on: E-HERO-03 · Outlier cited: [link/description]` — A "[We're hiring / open]" · B "[identity mirror — names the ICP's private ache, then reframes it]" · C "[same reframe as a question — statement vs question hooks]".
`E-FMT-01 · 📝 DRAFT · ICP [_] · Builds on: E-SOC winner` — the repeatable weekly format: [structure] · decide by [retention/follower quality metric] after [n] consecutive weeks.

> 💡 **In plain English:** a homepage headline is read by someone who *chose* to visit; a social hook interrupts someone who didn't. Packaging-first is the book-cover rule — people genuinely do judge books by covers, so design the cover before writing the book, and if no good cover exists, don't write that book. Hooks open a **curiosity gap**: a specific, emotional information gap the reader can only close by reading on — and the gap must pay off, because clickbait welches on the promise and spends the trust you've been dripping into the bucket since §1.

> 🎓 **Teaching moment — Paddy Galloway:** the idea and its packaging decide most of a video's fate before a single frame is shot. Spend disproportionate time choosing *what* to make (by studying outliers, not averages) and *how it will be framed* — then execution merely has to not lose.

> 🎓 **Teaching moment — Yasin Mammeri:** virality is a system, not a lottery ticket. Strong hook, clear structure, one repeatable format run consistently — stripped of clickbait and cringe — beats sporadic brilliance, because a format compounds and a fluke doesn't.

### 6.7 · The Learning Ledger *(append-only — the compounding asset)* `RIES`

**In one line: the ledger is the notebook where every finished experiment leaves behind one sentence about the *customer* — and each sentence is the seed of the next experiment.**

**What it is, in plain words:** every time an experiment finishes, you write one dated line: what you ran, what happened, and — most importantly — **one sentence about the customer** (never about the copy). Ten experiments run without a ledger give you ten forgotten anecdotes. Ten experiments run *with* a ledger give you a theory of your customer that writes winning lines on demand.

| ID | Date | Experiment | Result | Learning (one sentence about the ICP, not the copy) | Feeds |
|---|---|---|---|---|---|
| L0 | [date] | cold start | — | Best current beliefs: [3 bullets from the quote bank] | E-HERO-01/02/03 |
| L1 | | | | | |

**How to write a ledger entry — the three-part recipe:**
1. **Who** — name the ICP the lesson is about (one, singular).
2. **What they did** — the behaviour the numbers showed, in plain words.
3. **What that means they'll do next** — the sentence must point at a next experiment. If it doesn't, it's an observation, not a learning — rewrite it.

**Worked examples** *(a Dubai nursery — same worked example as §0.1)*:

| | Entry | Verdict |
|---|---|---|
| ❌ **Bad** | "L3 · Cell B won the email test with a 34% open rate." | Describes the *copy*, not the customer. Generates nothing. In six months nobody will remember why B won. |
| ✅ **Good** | "L3 · ICP 2 (the relocating parent) opens for a named receipt ('rated 4.9 by 212 parents') but ignores warm curiosity lines — under time pressure she trades poetry for proof. → Feeds: E-HERO-02 should lead with the receipt, not the story." | Names the person, the behaviour, and the reason — and the arrow tells you exactly what to run next. |
| ✅ **Good (from a KILL)** | "L5 · ICP 1 does *not* buy on guilt-removal: three guilt-framed cells lost to plain proof in a row. Belief #1 in §6.1 is falsified. → Feeds: retire guilt frames; promote belief #2 to the top of the attack order." | A dead assumption is still a lesson — often the most valuable one. |

**Ledger rules:**
1. Learnings describe the **customer**, never the copy ("ICP 2 trades poetry for receipts under time pressure" — not "line B won").
2. **Append-only** — never edit or delete an old entry; if a later result contradicts it, write the new entry and note the tension. Contradictions are fuel for the quarterly meeting, not embarrassments to erase.
3. Every entry ends with a **"→ Feeds:"** arrow naming the experiment (or §-update) it sets up. An entry with no arrow is unfinished.
4. A learning that can't generate the next hypothesis is only an observation — rewrite it until it can.

**Quarterly: the pivot-or-persevere meeting `RIES`.** Read the ledger top to bottom and count:
1. **Three consistent entries about one ICP** → update that ICP's definition in §4 (*persevere, sharper*).
2. **Three contradicting entries** → the ICP or the positioning is wrong; change one **deliberately** (*rethink/pivot*) rather than drifting.
3. **That's the loop:** evidence → experiment → ledger → sharper ICP → sharper experiments.

> 💡 **In plain English:** the ledger is a lab notebook, and the "→ Feeds" arrow is what makes it an engine instead of a diary. Scientists don't trust memory and neither should marketers — the notebook is what turns ten scattered results into one compounding theory. The quarterly meeting exists because there are only two honest responses to evidence: double down on purpose, or change course on purpose. Drifting is the only wrong answer.

**✅ To-do — Experiments**
- [ ] Fill the riskiest-assumption table (6.1) and rank it
- [ ] Write ≥4 challenges to existing client lines (always incl. the live H1 + subhead)
- [ ] Fill one hero card per ICP with committed expected winners and read dates
- [ ] Build subject + hook cards, each citing a "Builds on" entry and (for social) an outlier
- [ ] Start the outlier file; design the first repeatable format (`E-FMT-01`)
- [ ] Create the ledger with an L0 entry; diarise the quarterly pivot-or-persevere meeting
- [ ] Copy every card into the Appendix A worksheet before launch

---

## 7 · Pricing psychology — the fees/pricing page
*Purpose: make the price list itself another trust receipt.*

*Current-state critique: [what the page leads with] · [which generous moves are buried] · [where small print signals distrust].*

**Six principles:** 1 · **Transparency IS positioning** (competitors hide prices; publishing everything is the zag). 2 · **Anchor with the full option**, shown first — *anchor honestly: [the maths making it genuinely best value]*. 3 · **A marked default** ("most [customers] choose") `[UNVERIFIED — check real data]`. 4 · **Loss aversion, respectfully** — "keep [amount]", never "discount". 5 · **Pain-timing as care** — [move the cost to when it hurts least], said as care. 6 · **Kill the asterisk** — every figure carries its plain-English consequence right beside it.

**Page designs to test** as experiment cards (`E-FEES-01`): [interactive configurator] vs [plan cards] vs [honest ledger] — decide by [metric].

**Money register:** full prices always, never "from…" · the customer's unit, not the industry's · *keep*, not *save* · CTA is a conversation, never a checkout.

> 💡 **In plain English:** at premium prices, honesty outsells persuasion — a fully published, plainly explained price list is another coin in the trust jar. Asterisks read as small print, and small print reads as something to hide. And "keep AED 1,000" beats "get 1,000 off" for the same reason people guard their wallet harder than they chase a bargain: we fight hardest for what already feels like ours — and "discount" cheapens a premium brand.

**✅ To-do — Pricing**
- [ ] Critique the current fee page against the six principles
- [ ] Verify the "most choose" claim against real enrolment/sales data
- [ ] Rewrite every asterisk as an inline plain-English consequence
- [ ] Spec 2–3 page designs as experiment cards

---

## 8 · Website requirements
*Purpose: turn the strategy into a page order — proof first, feelings earned, ask last.*

**Goals, in order:** 1 · [Trust → primary conversion action] — never a cold form. 2 · Signpost [second offering] without diluting goal 1 (strict allocation: one band + footer link).
**The innovative bits:** [multi-path "choose how to meet us" booking] · [interactive proof-of-philosophy element] · [trust file — receipts, not marketing] · [brand-feature promise band + value-tagged reviews wall].
**Structure:** Nav → Hero (receipts + multi-path CTA) → Trust strip → Why [customers] choose us → Meet [founder] → [interactive proof] → [brand-feature] promise → Reviews wall (value-tagged) → [buyer-serving section] → [second offering] band → Visit/contact/footer. Sticky conversion bar throughout.
**Design · copy · imagery:** system from §0/§3 · [founder]'s first-person voice, governed by §5 · drop-zones for real photos — **no stock; the truth is the asset.**

> 💡 **In plain English:** the page order *is* the argument, like a good courtroom case: exhibits first, closing speech last. "Never a cold form" means the conversion is always a human conversation (tour, call, message) — because what's really being sold is trust in people.

**✅ To-do — Website**
- [ ] Confirm the primary conversion action and the 2–3 meeting paths
- [ ] Choose the interactive proof element
- [ ] Write the photography brief (real people, real place, no stock)

---

## 9 · MASTER TO-DO SUMMARY *(pull every unchecked item here, grouped — this is the client's punch list)*

| Category | Items | Owner | By |
|---|---|---|---|
| 🔍 **Evidence & verification** | [unverified trust drips · unvalidated values · "most choose" claim] | | |
| ✍️ **Copy** | [mined vocabulary list · challenged lines · hero/subject/hook cells] | | |
| 🎨 **Design & styling** | [palette confirmation · decision log · photography brief] | | |
| 🧪 **Experiments** | [riskiest-assumption table · ledger L0 · first 3 experiments · outlier file · quarterly review date] | | |
| 🌐 **Website** | [conversion paths · interactive element · page build] | | |
| 💷 **Pricing** | [fee-page rewrite · design tests] | | |

**First 3 experiments, in order:** 1 · `E-SUBJ-[n]` (cheapest, fastest frame signal — the wind tunnel) → 2 · `E-HERO-[n]` (promote the winning frame; now testing execution) → 3 · `E-FEES-[n]` (pricing, in the winning register). *Sequence cheap-and-fast → expensive-and-slow, so every costly test inherits a validated frame — and check the sequence still attacks the riskiest assumption first (6.1).*

> **Open questions (max 7):** [every `UNVERIFIED` tag above lands here]

### 9.1 · THE RED-TEAM PASS *(mandatory before delivery — the last section written, the first quality gate)*
Before the document ships, adopt the voice of a rival strategist paid to embarrass this one, and answer in writing:
1. **The five misses:** list ≥5 specific insights, quotes, or receipts this document could be accused of missing. For each: fold it in now, or state in one line why it's excluded.
2. **The buried asset:** name the single strongest asset still under-placed after §3's audit. If none, say so and defend it.
3. **The weakest quote:** which §2 quote is doing the least work? Replace it or cut it.
4. **The unfollowed link:** list every external source the client's own pages cite — were all fetched? Any not fetched is a defect.
5. **The satisficing check:** for every table in this document that was filled to exactly its template row-count, confirm the corpus was exhausted — or add rows.
A document that skips this pass is a draft, whatever its title says.

---

## APPENDIX A · EXPERIMENT TRACKER *(one row per experiment, kept live)*
*Purpose: §6 designs the experiments; this page runs them. Print it, pin it, or keep it as the team's shared sheet.*

**In one line: this is the training log — if a row is blank the experiment isn't real yet, and when a row finishes, the "What do I run next?" guide below tells you mechanically what to launch next.**

### A.1 · How to use it — four steps, no exceptions
1. **Before launch:** copy the card from §6 into a row. Write down which cell you *predict* will win, and — crucially — write the **read date** now (the calendar day you'll judge the result). Choosing the judging day *before* you see any numbers is what stops wishful early calls ("peeking").
2. **At launch:** fill in the launch date, flip the status to 🟢 LIVE — then don't touch the row until the read date. Not even a peek.
3. **On the read date:** write the actual number next to the pass-mark, flip to 🔍 READ, and pick **exactly one** of four actions (see A.3). One. Picking two means you haven't decided.
4. **To close:** write the one-sentence lesson in the ledger (§6.7), copy its ID (e.g. `L4`) into this row, flip to 📒 LOGGED. **No ledger ID = not finished** — the experiment officially never happened.

### A.2 · The tracker

| ID | Status | ICP | Bet (one line) | Scored by + pass-mark | Sample / time | Predicted winner | Launched | Read date | Actual result | Action (ship / tweak / kill / rethink) | Ledger ID | Feeds next |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| *WORKED EXAMPLE (a Dubai nursery — study this row, then delete it):* E-SUBJ-01 | 📒 | ICP 2 | Receipts beat curiosity for time-poor parents | open rate ≥ 30% | 800 sends / 48h | C (curiosity) | 03 Mar | 05 Mar | **B (receipt) won: 34% vs C 26%** | SHIP — B's frame rolls out | L3 | E-HERO-02 now leads with the receipt, per L3 |
| E-SUBJ-01 | 📝 | ICP 1 | | open rate ≥ [x]% | [n] sends / 48h | | | | | | | E-HERO-01 |
| E-HERO-01 | 📝 | ICP 1 | | [CTA action] ≥ [x]% | [n] visits / [x] wks | | | | | | | |
| E-SOC-01 | 📝 | ICP 1 | | hold rate ≥ [x]% | [n] impressions | | | | | | | |
| E-FMT-01 | 📝 | [_] | | [retention metric] | [n] consecutive weeks | | | | | | | |
| E-FEES-01 | 📝 | [_] | | [metric] ≥ [x] | [n] / [x] wks | | | | | | | |
| | | | | | | | | | | | | |

*Reading the worked example, start to finish: the bet was written and the read date fixed **before** launch (steps 1–2) · the prediction (C) turned out wrong — that's fine, being wrong is the valuable outcome · on the read date the real numbers went in and ONE action was chosen (SHIP) · the lesson went to the ledger as L3 ("ICP 2 trades poetry for receipts under time pressure") · and the "Feeds next" cell says exactly how L3 changes the next experiment. That row is a finished experiment. A row missing any of those cells isn't.*

### A.3 · "What do I run next?" — the decision guide *(follow it like a flowchart)*

On the read date, compare the actual result to the pass-mark, then pick your action. **Each action tells you the next experiment — you never have to invent it:**

1. **A cell clearly won (beat the pass-mark)? → SHIP.**
   1. Roll the winning line out everywhere its channel lives.
   2. **Next experiment = the one named in this row's "Feeds next" cell**, updated to inherit the winner (e.g. the subject-line winner's *frame* — receipts vs feelings vs curiosity — becomes the leading cell of the next, more expensive test).
   3. Write the ledger entry; its "→ Feeds" arrow and this row's "Feeds next" cell must agree.
2. **Results were close, muddy, or the sample was too small? → TWEAK** *(a.k.a. iterate)*.
   1. Copy this row into a fresh row with a new ID (E-SUBJ-01 → E-SUBJ-02).
   2. Change **exactly one thing** (a sharper line, a bigger sample, a cleaner audience) — everything else stays identical.
   3. In the new row's "Bet", cite this row: "builds on E-SUBJ-01 / L[n]". Launch again.
3. **Every cell lost — the belief behind the test looks wrong? → KILL.**
   1. Go to the scariest-belief table (§6.1) and mark that belief **falsified** with the date and ledger ID.
   2. **Next experiment = whatever now sits at the top of the §6.1 table** — the new scariest belief inherits the attack.
   3. Celebrate briefly: a KILL just stopped you building a website, an email sequence and an ad budget on a false floor. Log it with the same care as a win.
4. **The result attacks the strategy itself (wrong customer? wrong positioning?) → RETHINK** *(a.k.a. pivot)*.
   1. Don't launch anything that depends on the challenged belief.
   2. Park it, marked ⚠, for the quarterly pivot-or-persevere meeting (§6.7) — strategy changes are made deliberately in that room, never mid-week in a spreadsheet.
   3. Meanwhile, run experiments from untouched branches of the §6.1 table.

**The 15-year-old check, applied to this page:** given any completed row, you should be able to answer "what do we run next?" using only (a) the Action column, (b) this guide, and (c) either the "Feeds next" cell (SHIP), a copy of the row (TWEAK), or the §6.1 table (KILL). If you can't, the row is missing a cell — fill it before moving on.

### A.4 · Tracker rules
1. **One row = one experiment = one changed thing = one score.** If a row needs two metrics to look good, split it into two experiments.
2. **Read dates are appointments, not suggestions.** Moving one after launch requires a written reason in the row.
3. **Every KILL is a win** — it saved you building on a false belief (§6.1). Log it with the same care as a ship.
4. **Review cadence:** scan this sheet weekly (anything past its read date?) · reconcile it against the ledger monthly (every 📒 row has a ledger ID; every ledger arrow has a row) · feed it into the quarterly pivot-or-persevere meeting.

> 💡 **In plain English:** this appendix is the difference between a gym plan and a training log. §6 is the plan; this page is where you record what you actually lifted, when, and — via the decision guide — what you'll lift next session. Plans impress; logs compound. And the guide exists so "what next?" is never a debate: the tracker answers it for you.

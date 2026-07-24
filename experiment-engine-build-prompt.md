# BUILD PROMPT — The Experiment Engine (live tool)
*(Paste into Claude alongside the client's strategy document. This tool sits on the Stage-2 backlog under decision D7 in DECISIONS.md: build it only after the 3 pilot clients prove the method. Even then, use it only after the loop has been run manually at least once — the tool enforces a process; it can't create the habit.)*

## GOAL
Build a single React artifact called **The Experiment Engine**: a live tool that runs the experiment tracker and learning ledger from the attached strategy document, enforces the process in code (not in advice), shows the founder the value of the approach, and recommends new ideas that can only enter the system as draft experiments. Seed it with the tracker rows and ledger entries from the attached document.

## MODULE 1 — Tracker board (enforcement, coded)
1. One card per experiment with its status pill: 📝 draft → 🟢 live → 🔍 read → 📒 logged. Each card carries a **result source** field — the named place its number will be fetched from (email platform, analytics, ad manager) — so a future agent knows where to fetch.
2. **Cadence lock (📝 → 🟢):** no card flips to live without a named follow-up owner and a calendar appointment for the read. Read dates snap to the client's fixed weekly Reading Day, so all matured experiments are read in one weekly sitting.
3. **Read-date lock:** the results field is disabled until the row's read date; show a countdown instead. No peeking is a rule the UI physically enforces.
4. **One action only:** on the read date, exactly one of SHIP / TWEAK / KILL / RETHINK can be selected. Selecting it fires the decision guide automatically:
   - **SHIP** → opens the experiment named in "Feeds next", pre-filled to inherit the winning frame.
   - **TWEAK** → clones the row with a new ID, requires exactly one field to be changed, auto-cites the parent row in "Builds on".
   - **KILL** → marks the linked belief in the scariest-belief list as falsified (with date + ledger ID) and surfaces the new top belief as "test this next".
   - **RETHINK** → flags the row ⚠ for the quarterly review and blocks launching any experiment that depends on the challenged belief.
5. **No ledger ID, no closure:** a row cannot reach 📒 without a linked ledger entry.

## MODULE 2 — Learning ledger (append-only)
1. No edit or delete controls exist in the UI. Contradictions are logged as new entries, never erased.
2. The new-entry form enforces the three-part recipe: **who** (one ICP) → **what they did** (plain words) → **what that means we'll do next**, plus a mandatory **"→ Feeds"** field naming the next experiment or section update.
3. Use the Claude API to draft the entry from the raw result the founder pastes; the founder approves or edits before it saves.

## MODULE 3 — Value dashboard (decision-grade numbers only)
Show: beliefs validated vs falsified · experiments closed vs open · prediction win-rate (how often the committed winner actually won — being often wrong is fine and say so) · average time from launch to logged lesson · a plain-English feed of the last five lessons.
**Banned:** impressions, followers, page views, or any vanity panel. If a number can't change a decision, it doesn't render.

## MODULE 4 — Delight Compass (innovation queue)
1. **Lens 1 — Evidence scan:** on request, use the Claude API to scan the ledger and the strategy doc's quote bank for opportunities to delight or exceed the client's customers.
2. **Lens 2 — Cross-Industry (after Rory Sutherland):** take a theme the evidence shows matters most to the ICP, scan other industries that solve the same theme for the same human feeling, and propose borrowings conversationally, teaching the founder why: "your ICP's evidenced theme is X; look what [brand] does in [industry]; you could try Y — explore this, or stay focused on existing experiments?"
3. Every suggestion must cite its source: Lens 1 cites **at least one ledger entry or verbatim customer quote**; Lens 2 cites its evidenced theme and is labelled **[HYPOTHESIS]**. Uncited ideas are not shown.
4. The only button is **"Add as 📝 DRAFT experiment card"** — it creates a tracker row in the backlog (it never jumps the queue) with a hypothesis, a scored-by metric, a pass-mark placeholder, and the citation in "Builds on". There is deliberately no "add to strategy" path: nothing enters the strategy except through a read experiment.

## MODULE 5 — State & versioning
1. Persist all state with the artifact storage API (window.storage) so it survives between sessions.
2. Every closed experiment appends a line to a change log; an **"Export changes"** button produces the "what changed since v1.x" text the founder pastes into Claude to regenerate the strategy document at the next version.

## CONSTRAINTS
Single artifact · British English · every screen must pass the 15-year-old test: it should always be obvious what to do next · the founder never types into the strategy itself from this tool — the tool feeds the document, the document stays the source of truth.

## ACCEPTANCE TESTS (build is done only when all seven pass)
1. A result cannot be entered before the read date.
2. A row cannot close without a ledger ID.
3. A saved ledger entry cannot be edited or deleted.
4. A Delight-Compass idea can only exit as a draft experiment card with a citation.
5. The dashboard contains zero vanity metrics.
6. An experiment cannot go 🟢 live without a follow-up owner and a calendar appointment.
7. A Cross-Industry suggestion without an evidenced theme citation is not shown.

# DECISIONS.md — Decided + Set
*The record of decisions from the 2026-07-24 grilling session. Each entry: the decision, the reason, and what would reopen it. Amendable — but deliberately, never by drift.*

---

## The business

**D1 · Bakery, not cookbook.** For the next 12–24 months this is a consulting practice with software leverage, not a software company. Stages 3–4 (self-serve product, platform) are options preserved, decided later from pilot evidence. *Reopens if: pilot evidence shows founders self-serve successfully without Hannah.*

**D2 · The customer gate.** Clients must already have customers and material (revenue, website, socials, reviews). Product/brand businesses primary, service businesses secondary. Defined by moment, not stage. *Reason: the core question — "do you know what your customers truly value, in their words?" — is unanswerable without customers.*

**D3 · The shop window says "growing but stuck."** Marketing leads with the strategically-fuzzy founder, not the fundraiser. Fundraisers welcome through the open door; deep customer knowledge produces a growth story as a side effect. *Reason: constant pain beats a two-month window, and it matches the soul of the offer.*

**D4 · Launch = 3 paying founding clients.** £750 founding price (full price £1,250 ≈ two days at current rate, sold as a fixed-price dish, never hours). Early adopters are interviewed; assumptions written before each engagement, surprises recorded after. *Reason: payment is the first real evidence; trivial money buys polite lies. The machine's speed is margin, not discount.*

**D5 · The dish.** Full v4 Strategy & Requirements document + assumptions ledger + first 3 experiments + one working session. Markdown first; styled HTML optional for pilots. Founder confirms/plugs gaps via the prioritised answer-box panel, or the system assumes and stamps it. No second "lite" recipe — the hour-budget decides trimming from evidence. 

**D6 · Pilot scorecard, fixed before cooking.** Proved only if: all 3 paid · a recorded "oh!" moment in every session · ≥2 of 3 run an experiment within 30 days · ≥2 would pay full price (or book/refer unprompted) · ≤~8 Hannah-hours per client. Fewer = not proved: fix the recipe, run 3 more. No advancing on a maybe.

**D7 · No founder-facing software until the method survives 3 real clients.** The pilots run on the private kitchen (this repo). Method-architecture decided now; software-architecture after pilots, from evidence. *Reason: with 3 clients, every hour on login screens is an hour not proving the recipe.*

## The system

**D8 · The constitution.** Evidence → interpretation → decision → action binds every document and engine. Nothing enters strategy except through the loop. See CONTEXT.md.

**D9 · One stamped side-door.** Strategist judgment may change strategy without an experiment, carrying a judgment stamp (reasoning + confidence + the future test that could kill it). *Reason: direction when evidence is thin is exactly what clients pay for; the stamp keeps it honest and makes the Hannah layer visible.*

**D10 · Pipeline order: examination before blood test.** The Strategy Generator always runs first on existing material. The Value Prop Validation Engine is prescribed when the offer itself tops the scariest-belief table — upstream in authority (its KILL reopens the strategy at the root), downstream in time. *Reason: the founding promise is immediate value from existing material, not a validation gauntlet.*

**D11 · The Reddit/AI Visibility Engine is ears and hands.** Intake (phases 1–3, 6) feeds the evidence layer; activation (phases 4–5) exits only as `E-VIS` experiment cards with scored-by metrics and read dates; the monthly audit closes the loop. *Reason: the hands must not bless their own work — only the ears can say it worked.*

**D12 · One Evidence Harvest.** Collection is unified in the master prompt (search cascade + buyer-question discovery merged); both engines become readers of one provenance-tagged store; only the monthly audit re-collects. Acceptance check for the doc update: neither engine loses a capability. *Reason: two independent crawls waste hours and let the system contradict itself.*

**D13 · Six soft judgment gates.** Contradictory evidence · positioning conflict · side-door use · KILL/RETHINK · quarterly pivot-or-persevere · vision/creative direction. The system always proceeds with a stamped default; gates are honest signposts. Posture: abundance — working with Hannah is the upsell, never a toll booth, never forced wow-moments.

**D14 · Canonical vocabulary.** The five-rung evidence ladder; Segment (auditioned) vs ICP (cast); TWEAK retires REVISE/iterate; template §2 renamed "validated values"; `[EVIDENCE]`/`[HYPOTHESIS]` the only labels. Full glossary in CONTEXT.md.

**D15 · The Cadence + Reading Day.** No experiment goes LIVE without a follow-up owner and calendar appointment (invite created at launch). Experiments are read in weekly batches: read date = first Reading Day after the sample matures. In pilots the owner is Hannah and the weekly scan is a billed-in service ritual. *Reason: a rule with no bell attached is a hope.*

**D16 · Result-source field now, automation later.** Every experiment card names where its result lives (email platform, analytics, ad manager) so a future agent knows where to fetch. Automated result-fetching and agentic reminders are Stage-2 backlog by design — not built before the pilots prove the method.

**D17 · The Cross-Industry Lens.** The Delight Radar gains a second lens: evidenced ICP themes → scan other industries solving the same theme → propose borrowings conversationally, teaching the founder why. Named thinker: Rory Sutherland. Guardrails: every borrowing cites its theme, enters as `[HYPOTHESIS]`, exits only as a 📝 DRAFT card in the backlog, offered at natural moments (post-close or quarterly), never jumping the queue. *Reason: strategy must not become only retrospective cumulative learning; this is the licensed entrance for newness — and a differentiator competitors can't copy tomorrow.*

**D18 · Process rule.** Any design decision touching the source documents must cite the specific sections affected in each document and check for cross-document overlap before proposing. (Encoded in CLAUDE.md; born from two catches Hannah made that the process missed.)

---

## Next planned pass

Grill each source document against CONTEXT.md and these decisions, one at a time, updating them in place:
1. `master-prompt-v4.md` — Evidence Harvest merge · vocabulary renames · judgment gates surfaced · Cross-Industry Lens generation step · result-source field · Cadence/Reading Day rules
2. `strategy-template-v4.md` — vocabulary renames · judgment stamps · gates · lens output section
3. `experiment-engine-build-prompt.md` — Cadence enforcement · Delight Radar second lens · result-source field · vocabulary
4. `value-prop-validation-engine.md` — TWEAK rename · ladder labels · prescribed-by-pipeline framing · Segment/ICP relationship
5. `reddit-ai-visibility-engine.md` — ears/hands split interfaces · harvest reader role · E-VIS card exits · vocabulary

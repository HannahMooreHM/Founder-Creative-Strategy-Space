---
status: proposed
---

# One shared domain language for the decision spine

The workflow docs each spoke a private dialect for the same ideas (quote bank /
`[EVIDENCE]` / tracker rows; scariest belief / `[HYPOTHESIS]`; ledger entries).
The orchestrator's memory instead holds exactly eight canonical objects — Evidence
item, Assumption, Strategic reading, Strategy snapshot, Experiment, Learning,
Decision, Proposed strategy update — defined in [CONTEXT.md](../../CONTEXT.md).
Decided with Hannah in
[Shared domain language for the decision spine](https://github.com/HannahMooreHM/Founder-Creative-Strategy-Space/issues/4).
This file records the decisions and trade-offs behind the glossary; it will be
marked accepted when that ticket closes.

## Decisions

1. **Eight objects, no ninth.** "Version" is deliberately not an object — it is a
   label on Strategy snapshots (and, per the versioning research, on prompts),
   the way a page number belongs to a book.

2. **One Evidence drawer; experiment results file as evidence.** Three
   distinguishable kinds — customer voice, checkable fact, observed result — with
   the kind label mandatory. The bright line is the value-prop engine's rule kept
   as law: out of our heads → Assumption; out of the world → Evidence item.
   *Trade-off:* results could have stayed on the Experiment object, but that
   would force a second provenance path; one drawer means one source-and-date
   treatment for everything the workspace shows a founder.

3. **Assumptions: born with a falsifier, ranked by blast radius, open →
   supported / falsified, dead ones kept on file.** "Supported" (not
   "validated") because evidence only ever props a belief up — support is
   provisional, falsification is permanent; a revived belief is a new assumption
   citing the old one. **Founder-facing rule:** the workspace never shows a bare
   "write your falsifier" prompt — it always offers worked example falsifiers,
   each with the implication of choosing it spelled out, plus at least two
   alternative options, so a founder who has never met the concept picks rather
   than invents.

4. **Reading is a mutable draft; approval freezes it into an immutable,
   append-only snapshot chain.** One reading per journey at a time; founder
   approval is a recorded Decision that turns it into Strategy snapshot v1; later
   change happens only as Learning → Proposed strategy update → approval → new
   version. Aligned with the versioning research: delivered work is never
   retro-regenerated. Two riders from Hannah: (a) each version's "what changed"
   line covers only the step from the immediately previous version — no
   cumulative history bloat; (b) the backstage records the **review delta**
   (reading-as-drafted vs snapshot-as-approved) and mines it for what the founder
   loved and what the reading missed — internal-only signal, and seed material
   for the map's "which orchestrator decisions to encode" fog patch. A further
   rider: each snapshot's delta line links to a **full version history** view —
   always generated from the snapshot chain, never hand-maintained as a separate
   changelog (one source, many views). The history page itself is built with the
   MVP surface screens (issue #22).

5. **Experiments adopt the Engine's enforced lifecycle wholesale.** Four stages
   (draft → live → read → logged; the status pills stay as founder-facing dress)
   and three laws: commit before launch (one variable, one metric + pass-mark,
   read date, predicted winner), no peeking before the read date, and no
   Learning, no closure. The read-date choice — ship / tweak / kill / rethink,
   exactly one — is recorded in the Decision drawer, not as a private field, so
   every consequential fork in a journey is one query. Kill marks the attacked
   assumption falsified; tweak clones with a citation to its parent; ship follows
   "feeds next"; rethink parks for the quarterly review. Incoming numbers file as
   observed-result evidence items. Enforcement is by process in the concierge
   era, by code later.

6. **Learnings keep the ledger's four laws, with the feeds arrow widened and
   the cold start named.** (a) A learning describes the customer, never the
   copy — "ICP 2 trades poetry for receipts under time pressure", not "line B
   won" — the rule that makes learnings compound into a theory of the customer
   instead of a pile of A/B trivia. (b) The three-part recipe is mandatory:
   who (one customer type) → what they did (plain words) → what that means
   they'll do next; anything that can't generate the next move is an
   observation, not a learning — rewritten until it can. (c) Append-only,
   forever: no edits, no deletions; a later contradiction gets its own new
   learning that names the tension — the same no-eraser discipline as the
   snapshot chain and the falsified-assumptions file. (d) Every learning ends
   with a **feeds arrow**, widened from the docs: it may name the next
   experiment, a Proposed strategy update, or explicitly say "end of loop for
   now" — it never just trails off. In this workspace changing the strategy is
   the product, so a learning's most important output can be the update
   itself, not only the next test. (e) One learning per experiment as the
   rule; the cold start as the exception — the journey's opening beliefs enter
   as a **seed learning** (the template's L0) drafted from the evidence
   corpus, so the first experiments don't pretend to appear from nowhere. The
   template's own analogy stands: a lab notebook where the arrow is the
   difference between a scientist's notebook and a diary.

7. **Proposed strategy updates: born from the spine, shaped as diffs, declines
   kept on file, one at a time.** (a) Born only from a citing chain, never
   from dictation — normally a Learning's feeds arrow. Hannah's rider: the
   **founder-hunch lane** keeps conviction moving. A hunch is a belief out of
   the founder's head, so it enters as an open Assumption (falsifier + blast
   radius) and may then propose the change immediately, without waiting for an
   experiment. Conviction is never blocked, only labelled: hunch-backed
   snapshot text carries assumption-only provenance, and holding up strategy
   text raises the assumption's blast radius so the next experiment naturally
   attacks it. (b) Shaped as a diff, not an essay: it names the section, shows
   before → after, and links its citation; the next snapshot is generated from
   snapshot + approved delta — one source, many views, as with the version
   history. (c) Three states: proposed → approved / declined. Approval is a
   recorded Decision and the only door into a new snapshot version (law since
   decision 4). Declined updates stay on file, dated, with the founder's
   reason — the same no-eraser discipline as falsified assumptions, and mined
   like the review delta for where founder conviction lives. (d) One open
   update per journey at a time; a second queues — the founder is never shown
   two competing rewrites of the same section. (e) Declining doesn't reopen
   the citing learning; a later change of heart is a fresh update citing the
   same learning — the same pattern as reviving a falsified assumption.

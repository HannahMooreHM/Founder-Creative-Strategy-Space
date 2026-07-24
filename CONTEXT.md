# Founder Strategy Workspace — Decision Spine

The shared language for the thin orchestrator: the eight kinds of thing its memory
holds across the release-one journey (minimal inputs → evidence extraction → initial
strategic reading → founder review → strategy snapshot → one experiment → one
learning → one proposed strategy update). Every workflow doc files into these terms;
no doc keeps a private dialect. Decided in
[Shared domain language for the decision spine](https://github.com/HannahMooreHM/Founder-Creative-Strategy-Space/issues/4).

## Language

**Evidence item**:
A record of something the real world said, in exactly one of three kinds — always
carrying its kind, source and date. If it came out of our heads it is an Assumption;
if it came out of the world it is an Evidence item. Nothing else exists.
_Avoid_: quote bank entry, trust drip, `[EVIDENCE]`, mined phrase

**Customer voice** (kind of Evidence item):
A verbatim customer quote — review, forum post, interview answer — ≤15 words, with platform and date.

**Checkable fact** (kind of Evidence item):
A receipt anyone can verify: an award, a rating, a policy, years operating.
_Avoid_: receipt (in new writing; the strategy docs' "receipt" maps here)

**Observed result** (kind of Evidence item):
A number the world produced when we poked it — an open rate, a reply rate, a
pre-order count — always linked to the experiment that produced it.

**Assumption**:
A belief the strategy leans on, born with a falsifier and a blast-radius rank,
living in one of three states: open → supported / falsified. Falsified assumptions
never leave the file.
_Avoid_: scariest belief, riskiest assumption, `[HYPOTHESIS]`, linked belief, validated (use supported)

**Falsifier**:
The observation that would kill an assumption — "this is wrong if prospects say ___ / do ___".
An assumption without one is a worry, not an assumption.

**Blast radius**:
An assumption's rank by "if this is wrong, what collapses?" — it decides attack
order: experiments aim at the top of the list.

**Strategic reading**:
The interpretation drafted from the evidence — what we think it means. A mutable
draft, one per founder journey at a time, citing evidence items and assumptions
by link, never by pasted copy. Founder approval freezes it into a Strategy snapshot.

**Strategy snapshot**:
The strategic reading after founder approval: immutable, versioned (v1, v1.1, …),
never edited — only succeeded via an approved Proposed strategy update. Each new
version opens with a "what changed" line covering only the step from the previous version.
_Avoid_: strategy document (the premium consultancy deliverable is a different thing), positioning one-pager

**Review delta** (internal, never founder-facing):
The backstage diff between the reading as drafted and the snapshot as approved —
mined for what the founder is loving and for gaps the reading should have caught.

**Experiment**:
One test with one variable, one decision metric with a pass-mark, a fixed read
date and a committed predicted winner — all set before launch. Lives in exactly
one of four stages: draft → live → read → logged. No peeking before the read
date; cannot reach logged without its Learning. The card and the tracker row are
one object, not two.
_Avoid_: test, tracker row (as a separate thing from the card)

**Learning**:
The one-sentence lesson about the customer that a finished experiment leaves
behind — who (one customer type) → what they did (plain words) → what that
means they'll do next. It describes the customer, never the copy; if it cannot
generate the next move it is an observation, not a learning — rewrite until it
can. Append-only, forever: no edits, no deletions; a later contradiction gets
its own new learning that names the tension. Every learning ends with a feeds
arrow. One learning per experiment, with the seed learning as the only exception.
_Avoid_: ledger entry, lesson, insight

**Feeds arrow** (part of a Learning):
The mandatory closing pointer on every learning: the next experiment, a
Proposed strategy update, or an explicit "end of loop for now". A learning
never just trails off — the arrow is what makes the ledger a lab notebook
that runs an engine, not a diary.

**Seed learning** (kind of Learning):
The journey's opening beliefs, drafted from the evidence corpus rather than
from a finished experiment — the strategy docs' L0 cold-start entry. The only
learning an experiment didn't produce; it feeds the first experiments.

**Decision**:
A record of a choice a human made at an approval point: who chose, what, and when.
Includes founder approvals (reading → snapshot, proposed updates) and the
read-date choice on an experiment — ship / tweak / kill / rethink, exactly one.
_Avoid_: gate outcome, action (bare), approval (bare)

**Proposed strategy update**:
The suggested change a learning generates, waiting for founder approval to become the next snapshot version.
_Avoid_: export changes, §-update

## Notes

- **Version** is deliberately not an object: it is a label every strategy snapshot
  carries, like a page number belonging to a book.
- Founder-facing vocabulary versus these internal terms: to be decided (same ticket).

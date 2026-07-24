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
   for the map's "which orchestrator decisions to encode" fog patch.

Context: https://github.com/HannahMooreHM/Founder-Creative-Strategy-Space/issues/8

# Prompt and model versioning for a mostly-manual productised service

Researched 2026-07-24. All Anthropic documentation, the Langfuse documentation source, and the `simonw/llm` documentation were fetched directly and quoted verbatim. A few practitioner/vendor pages were unreachable from this environment (network policy); claims from those are drawn from search-engine extracts and are marked **[search extract]** — treat exact wording as unverified.

---

## Summary — minimal viable practice (RECOMMENDATION)

This section is recommendation, fitted to this product: prompt documents (`master-prompt-v4.md`, `strategy-template-v4.md`) kept in git and pasted into a Claude Project, producing one client deliverable per engagement. Everything here uses git plus one plain-text file. Nothing requires new infrastructure. The facts these recommendations rest on are in the Evidence section.

### 1. Prompt registry = the git repo you already have

- Keep prompts as Markdown files in this repo (already the case). Git is the registry; every practitioner source surveyed treats a git repo of prompt files as the baseline pattern, and platform "prompt registries" reduce to the same three primitives: immutable versions, a pointer to the version in use, and per-output linkage (Evidence §4, §6).
- Keep the existing `-vN` filename suffix as the **major version only**: bump it when the method or the deliverable's structure changes (a client could tell the difference). For wording tweaks, just commit — the git short-hash is the fine-grained version. Do not create `-v4.1`, `-v4-final2` files.
- When the template and master prompt must move together (they pair), bump both in one commit so one hash identifies the pair.

### 2. Record per output (one line, at delivery time)

Append one line per delivered output to a `run-log.md` table in this repo (or a footer inside your internal copy of the deliverable — not the client-facing copy):

| Field | Example | Why (see Evidence) |
|---|---|---|
| Date (ISO) | `2026-07-24` | Serving infrastructure can shift behaviour even on a pinned model ID, so the date matters independently of the model ID (§1) |
| Model | `Claude Opus 4.8` / `claude-opus-4-8` | Model IDs are pinned snapshots; the ID plus date reproduces the setup (§1). In claude.ai, record the exact name shown in the model picker |
| Prompt version | `master-prompt-v4 @ abc1234` | File + git short-hash pins the exact wording (§4, §5) |
| Template version | `strategy-template-v4 @ abc1234` | The deliverable's structure is part of the prompt (§6) |
| Input reference | `clients/acme/brief-2026-07.md` | A pointer to (or digest of) the client inputs makes the output explainable later; every logging tool surveyed stores the input alongside the output (§6) |
| Deviations | `none` / `extra Q&A round on pricing` | Manual services deviate; note it or the record lies |

That is the whole schema. A parameters column is unnecessary for this product: Anthropic has deprecated `temperature`/`top_p`/`top_k` on current models, and claude.ai exposes no sampling knobs to record (§1).

### 3. Regeneration triggers (decide once, stop re-litigating)

- **Model retirement (forced).** Anthropic gives at least 60 days' notice and names a replacement; retired models simply stop working (§2). Trigger: on a deprecation notice, re-run 3–5 representative past briefs (a scaled-down "golden set", §7) on the replacement model, compare against their known-good outputs, adjust the prompt per Anthropic's migration guidance (§3), then switch. Do this well before the retirement date, not the week of.
- **Voluntary model change.** Same golden-set check before switching. Never switch silently mid-engagement.
- **Prompt major bump (`v4` → `v5`).** Applies to new engagements; regenerate in-flight deliverables only. **Never retro-regenerate delivered work** — it keeps its provenance line, which is the point of having one.
- **Prompt minor edits (a commit, no bump).** Future outputs only; no regeneration, no golden-set run required unless the edit was prompted by a defect.
- **Defect found in a delivered output.** Regenerate that one deliverable, add a new provenance line, mark the old line superseded.

### 4. What NOT to adopt

No prompt-management platform, no observability stack, no database. The platform features (immutable versions, deployment labels, output linkage) map one-to-one onto git commits, the `-vN` filename, and the run-log line (§6). The practitioner consensus is that git is the preferred registry at small scale, and platforms earn their keep only when non-technical stakeholders must edit prompts without touching the repo (§4) — not the situation here, where the founder is the operator.

---

## Evidence

### §1. Anthropic: model IDs are pinned snapshots — record the ID, but also the date

Anthropic's model IDs and versioning page (fetched directly):

> "Each Claude model ID identifies a pinned version of the model. When you use a model ID in an API request, the underlying model remains constant for the lifetime of that ID."
>
> "Anthropic does not update the weights or configuration of an existing model ID. When an updated version is available, it ships under a new model ID."

From the Claude 4.6 generation onwards, even dateless IDs (`claude-sonnet-4-6`, `claude-opus-4-8`) are pinned snapshots, not evergreen pointers. Before 4.6, dateless names such as `claude-sonnet-4-5` are **aliases** that "resolve to the most recent dated snapshot" — so for pre-4.6 records, the dated ID (`claude-sonnet-4-5-20250929`) is the correct thing to write down, not the alias. Source: https://platform.claude.com/docs/en/about-claude/models/model-ids-and-versions

Why the date column still matters even with pinned IDs:

> "Occasionally, infrastructure updates produce minor differences in observable behavior even when the model ID and weights have not changed."

(Same page, "Model weights versus serving infrastructure".)

On parameters: Anthropic's deprecations page records that `temperature`, `top_p` and `top_k` are deprecated on Claude Opus 4.7 and later ("Returns a 400 error when set to a non-default value"), with prompting recommended instead. Source: https://platform.claude.com/docs/en/about-claude/model-deprecations (API parameter deprecations section). Hence "parameters" is not a load-bearing metadata field for this product.

### §2. Anthropic: deprecation policy — retirement is the one forced regeneration trigger

From the model deprecations page (fetched directly), lifecycle is Active → Legacy → Deprecated → Retired:

> "**Retired:** The model is no longer available for use. Requests to retired models will fail."
>
> "Anthropic notifies customers with active deployments for models with upcoming retirements, providing at least 60 days' notice before model retirement for publicly released models."
>
> "Deprecated models are likely to be less reliable than active models."

Each deprecation names a recommended replacement, and Anthropic's stated best practice is to "test your applications with newer models well before the retirement date". Partner platforms (Amazon Bedrock, Google Cloud) set their own retirement schedules. Source: https://platform.claude.com/docs/en/about-claude/model-deprecations

Practical consequence: a small team does not choose whether model changes happen — only when, within a window of roughly 60+ days. The regeneration policy above is built around that window.

### §3. Anthropic: prompt changes are empirical, and model changes are prompt-revalidation events

The prompt engineering overview (fetched directly) states the prerequisites for any prompt iteration:

> "This guide assumes that you have: 1. A clear definition of the success criteria for your use case 2. Some ways to empirically test against those criteria 3. A first draft prompt you want to improve"

Source: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview

The eval-design page recommends task-specific test cases ("Design evals that mirror your real-world task distribution"), automation where possible, and volume over hand-graded perfection, with the workflow "test cases → preliminary prompt → iterative testing and refinement → final validation → ship". Source: https://platform.claude.com/docs/en/test-and-evaluate/develop-tests

Anthropic's prompting best-practices page maintains **model-specific** guidance pages (e.g. "Prompting Claude Sonnet 5", "Prompting Claude Opus 4.8") and a "Migration considerations" section for prompts moving between model generations — e.g. "Tune anti-laziness prompting: … Claude 4.6 models are more proactive and may overtrigger on instructions that were needed for previous models." Source: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices

This is direct vendor evidence that a prompt validated on one model is not automatically valid on the next — i.e. a model change should trigger a prompt re-check, which is why the golden-set step sits inside the model-change trigger above.

### §4. Prompt registry patterns: prompts as versioned files in git

Hamel Husain (practitioner, AI evals consultancy), "How should I version and manage prompts?" — **[search extract]**; hamel.dev was unreachable from this environment, and the following claims were consistent across two independent search extracts of the page: the preferred approach is storing prompts in git, treated as software artifacts that are versioned, reviewed, and deployed atomically with the application code; there is an unavoidable tension between keeping prompts close to the code and giving non-technical stakeholders an environment they can access; the GitHub web interface and GitHub Desktop make git approachable for non-technical collaborators; dedicated prompt-management tools (Arize, Braintrust, LangSmith) are the alternative when that tension bites. Source: https://hamel.dev/blog/posts/evals-faq/how-should-i-version-and-manage-prompts.html

Supporting pattern detail from a prompt-engineering course page — **[search extract]** (page unreachable directly): store prompts as plain `.txt`/`.md` files (or YAML/JSON when templated) in a dedicated `prompts/` directory in the project repo, treated "like any other development artifact". Source: https://apxml.com/courses/prompt-engineering-llm-application-development/chapter-3-prompt-design-iteration-evaluation/version-control-for-prompts

### §5. Semantic versioning of prompt documents

Several vendor guides converge on the same SemVer adaptation — **[search extract]** (pages unreachable directly; wording per search extracts):

- **Major** — breaking changes: fundamental restructuring of the prompt's logic, output-format changes that break downstream consumers, task redefinition, or switching model.
- **Minor** — backward-compatible improvements: added instructions, refined wording, new examples.
- **Patch** — typo/formatting fixes.
- The golden rule is **immutability**: a created version stays locked; changes produce a new version.

Sources: https://www.braintrust.dev/articles/what-is-prompt-versioning ; https://latitude.so/blog/prompt-versioning-best-practices ; https://www.getmaxim.ai/articles/prompt-versioning-best-practices-for-ai-engineering-teams/

Assessment (recommendation, not fact): full three-part SemVer is over-engineered for a two-file prompt set operated by one person. The scheme above keeps only the distinction that matters — breaking (filename bump) vs non-breaking (git commit) — which preserves the SemVer major/minor semantics without ceremony.

### §6. What metadata matters per output — from tools that do this at scale

**Langfuse** (open-source LLMOps; docs fetched directly from the documentation source repo, github.com/langfuse/langfuse-docs, published at langfuse.com):

- The prompt object is `{name, type, prompt, version}` plus optional config: "Versions provide an immutable history of every prompt change. Each update creates a new version (1, 2, 3...)" while "Labels are pointers to specific versions" (`production`, `latest`, custom). Source: https://langfuse.com/docs/prompt-management/data-model
- Model choice and parameters are stored **with the prompt version**, not per call: the config is "an optional JSON object attached to each prompt that stores structured data such as model parameters (like model name, temperature), function/tool parameters, or JSON schemas" and "is versioned together with the prompt". Source: https://langfuse.com/docs/prompt-management/features/config
- Outputs are tied back to prompt versions: "Link prompts to traces to analyze performance by prompt version." Source: https://langfuse.com/docs/prompt-management/overview

**`llm` CLI** (Simon Willison; docs fetched directly from github.com/simonw/llm): "`llm` defaults to logging all prompts and responses to a SQLite database." The per-response record includes `model`, `prompt`, `response`, `conversation_id`, and `datetime_utc` — i.e. a canonical minimal per-output schema from a widely used lightweight tool: model + input + output + grouping id + timestamp. Source: https://github.com/simonw/llm/blob/main/docs/logging.md (published at https://llm.datasette.io/en/stable/logging.html)

Reading across both: the industry-essential per-output metadata is (a) model identifier, (b) prompt version, (c) timestamp, (d) the input (stored or referenced), (e) the output itself. The run-log schema in the Summary is exactly this set, with "deviations" added because a manual service, unlike an API pipeline, can depart from the script.

### §7. How small teams decide when to regenerate

Regression-testing practice for LLM outputs — **[search extract]** (pages unreachable directly): re-run a fixed, versioned "golden" dataset of representative inputs after every model or prompt change and compare scores/outputs against the previous run; small teams keep golden sets small enough to run on every change; scheduled re-runs catch upstream drift. Sources: https://futureagi.com/blog/prompt-regression-testing-2026/ ; https://futureagi.com/glossary/golden-dataset/ ; https://futureagi.com/glossary/llm-regression-testing/

Anthropic's own version of the same trigger, verbatim (deprecations page, fetched directly): "To help measure the performance of replacement models on your tasks, consider thorough testing of your applications with the new models well before the retirement date."

Assessment (recommendation, not fact): for a productised service producing documents rather than API responses, the "golden set" is 3–5 past client briefs whose outputs you know were good, and "re-running the evals" is reading the regenerated documents side-by-side with the originals. No harness needed. The delivered-work rule (never retro-regenerate) has no single citable source; it follows from the immutability principle in §5 and from the commercial fact that a delivered document is a completed contract artefact — marked here as this document's own recommendation.

---

## Source list

Fetched directly:

1. Anthropic — Model deprecations: https://platform.claude.com/docs/en/about-claude/model-deprecations
2. Anthropic — Model IDs and versioning: https://platform.claude.com/docs/en/about-claude/models/model-ids-and-versions
3. Anthropic — Models overview: https://platform.claude.com/docs/en/about-claude/models/overview
4. Anthropic — Prompt engineering overview: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview
5. Anthropic — Prompting best practices (incl. migration considerations): https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices
6. Anthropic — Define success criteria and build evals: https://platform.claude.com/docs/en/test-and-evaluate/develop-tests
7. Langfuse prompt-management docs (via source repo langfuse/langfuse-docs): https://langfuse.com/docs/prompt-management/data-model , https://langfuse.com/docs/prompt-management/features/config , https://langfuse.com/docs/prompt-management/overview , https://langfuse.com/docs/prompt-management/features/prompt-version-control
8. simonw/llm — Logging to SQLite: https://github.com/simonw/llm/blob/main/docs/logging.md

Via search extracts only (pages blocked by this environment's network policy; wording unverified against the page itself):

9. Hamel Husain — How should I version and manage prompts?: https://hamel.dev/blog/posts/evals-faq/how-should-i-version-and-manage-prompts.html
10. Braintrust — What is prompt versioning?: https://www.braintrust.dev/articles/what-is-prompt-versioning
11. Latitude — Prompt versioning best practices: https://latitude.so/blog/prompt-versioning-best-practices
12. Maxim — Prompt versioning best practices: https://www.getmaxim.ai/articles/prompt-versioning-best-practices-for-ai-engineering-teams/
13. ApX ML — Version control for prompts: https://apxml.com/courses/prompt-engineering-llm-application-development/chapter-3-prompt-design-iteration-evaluation/version-control-for-prompts
14. FutureAGI — Prompt regression testing / golden datasets: https://futureagi.com/blog/prompt-regression-testing-2026/ , https://futureagi.com/glossary/golden-dataset/

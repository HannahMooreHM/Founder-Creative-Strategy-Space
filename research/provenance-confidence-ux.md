Context: https://github.com/HannahMooreHM/Founder-Creative-Strategy-Space/issues/7

# Provenance and confidence presentation: precedents survey

How existing products present AI-generated claims, confidence levels, citations and
assumptions to non-expert users — and which patterns demonstrably aid comprehension
and trust. Feeds the provenance/confidence scheme (#10) and the reading & snapshot
UI prototype (#22).

**Method note.** Primary sources were used wherever the network permitted. Two were
fetched in full (Microsoft HAX toolkit Guideline 2; Anthropic Citations API docs).
Most other primary pages (vendor help centres, journal sites, arXiv) were blocked at
the network gateway from this environment, so their content was obtained through
search-engine extracts of the named primary source; each claim below cites the URL
it came from. Items resting only on third-party descriptions of a product's UI are
marked [UNVERIFIED]. Nothing here is quoted from memory without a source.

---

## Decisive summary — eight patterns #10 and #22 should consider

### 1. Two-layer citation UI: claim-level markers plus a consolidated source panel

Every major AI answer engine has converged on the same shape: a small numbered
marker attached to the specific sentence or claim, plus a collapsed panel ("Sources",
"Show all") holding the full source list. Perplexity attaches numbered chips per
sentence with a source strip above the answer; ChatGPT search shows inline citations
you can hover, with a Sources button opening a sidebar; Copilot uses footnote-style
numbered citations with a "Show all" right-hand panel; Google AI Overviews shows
inline links plus a right-hand source panel with hover previews.

- Proven in: [Perplexity](https://www.perplexity.ai/help-center/en/articles/10352895-how-does-perplexity-work), [ChatGPT search](https://help.openai.com/en/articles/9237897-chatgpt-search), [Copilot/Bing](https://eaxmedia.com/bing-copilot-inline-citations-sidecards-update/), [Google AI Overviews](https://blog.google/products-and-platforms/products/search/explore-web-generative-ai-search/).
- Good for: keeping the reading surface clean while making every claim individually
  checkable. The unit of provenance is the **claim, not the document** — a
  bibliography at the end of a strategy document would be the weakest version of
  this pattern.
- Caveat: this pattern aids *verifiability*, not verification — see pattern 8a.

### 2. Quote-anchored provenance: bind the claim to the exact passage, one click away

The strongest tools do not link to a document; they link to the *sentence*. The
Anthropic Citations API returns "the exact passages that support each claim"
(`cited_text` with document location) rather than prompt-generated references.
Elicit lets users click any extracted answer cell and flip through the supporting
quotes shown in context of the paper, with an explanation for every data point.
Consensus renders only "word-for-word quotes from papers rather than AI-generated
text" specifically to prevent hallucination. NN/g's recommendation for fixing the
verification problem is the same: "deep links to referenced passages, or showing
them in a preview of the source", to collapse the interaction cost of checking.

- Proven in: [Anthropic Citations docs](https://platform.claude.com/docs/en/build-with-claude/citations) (fetched in full), [Elicit](https://elicit.com/blog/living-documents-ai-ux) / [IntuitionLabs on Elicit](https://intuitionlabs.ai/articles/elicit-data-extraction-clinical-papers), [Consensus](https://help.consensus.app/en/articles/9922673-how-consensus-works), [NN/g](https://www.nngroup.com/articles/ai-chatbots-discourage-error-checking/).
- Good for: the workspace's **mined-verbatim** provenance class. A "mined verbatim"
  label should always carry the verbatim passage itself (or a one-click preview of
  it), not merely a pointer to the transcript it came from.

### 3. A small set of categorical confidence tiers, each mapped to an action — not numeric scores

Google's PAIR guidebook: bucket confidence into categories such as High/Medium/Low,
and "clearly indicate what action a user should take under each category of
confidence"; "statistical information like confidence scores can be challenging for
users to understand", so only show confidence at all if research confirms it improves
the user's decision. The mature decision-support precedents are all tiered, not
numeric: GRADE rates certainty of evidence High/Moderate/Low/Very-low; UpToDate
collapses it to grades 1A–2C where the digit means "how strongly should you act"
and the letter means "how good is the evidence"; USPSTF uses A/B/C/D/I; Morningstar
uses Gold/Silver/Bronze/Neutral/Negative and explicitly separates its quantitative
star rating from its qualitative analyst rating "to reduce complexity".

- Proven in: [PAIR guidebook](https://pair.withgoogle.com/chapter/explainability-trust/), [GRADE (CDC handbook)](https://www.cdc.gov/acip-grade-handbook/hcp/chapter-7-grade-criteria-determining-certainty-of-evidence/index.html), [UpToDate grading guide](https://www.wolterskluwer.com/en/solutions/uptodate/policies-legal/grading-guide), [USPSTF](https://www.uspreventiveservicestaskforce.org/uspstf/about-uspstf/methods-and-processes/grade-definitions), [Morningstar](https://www.morningstar.com/company/ratings).
- Good for: the #10 confidence tiers. Two independent axes — *how solid is the
  evidence* and *how much should this change what you do* — are the proven shape
  (UpToDate's 1A–2C). Each tier must answer "so what should I do with this claim":
  e.g. *act on it / check before shipping / treat as a hypothesis to test*.
- Note PAIR's alternative when a score would mislead: show **N-best alternatives**
  instead of a confidence indicator — for the workspace, that is "here are the two
  readings we considered" rather than "we are 71% sure".

### 4. Calibrated verbal labels only work when anchored — pair words with ranges, keep the lexicon tiny

The IPCC's calibrated language (virtually certain >99%, very likely >90%, likely
>66%…) is the canonical tiered-language scheme, but Budescu's multi-country studies
(25 samples, 24 countries) found the public reads these terms *regressively* —
"very likely" is interpreted as near 50% — and consistency with the intended
meaning rose from 27% to 40% only when the word was shown **together with its
numeric range** ("very likely (90–100%)"). Separately, van der Bles et al. found
in five experiments (n=5,780, including a BBC field experiment) that communicating
uncertainty as a **numeric range barely dents trust** in the number or the source,
while vague verbal-only uncertainty statements reduce perceived reliability more.
Honest, anchored uncertainty is cheap; woolly hedging is not.

- Proven in: [IPCC AR5 uncertainty guidance note](https://www.ipcc.ch/site/assets/uploads/2017/08/AR5_Uncertainty_Guidance_Note.pdf), [Budescu et al. 2009](https://moodle2.units.it/pluginfile.php/232175/mod_resource/content/1/Budescu,%20Broomell,%20Por%20(2009).pdf) and [the 24-country replication](https://www.researchgate.net/publication/275118595_The_Interpretation_of_IPCC_Probabilistic_Statements_Around_the_World), [van der Bles et al., PNAS 2020](https://www.pnas.org/doi/abs/10.1073/pnas.1913678117), framework in [van der Bles et al., R. Soc. Open Sci. 2019](https://royalsocietypublishing.org/doi/10.1098/rsos.181870).
- Good for: naming the #10 tiers. If tier names are words ("solid", "provisional",
  "guess"), define each once, visibly, in terms of what it means operationally —
  and never let free-text hedge words ("probably", "likely") appear outside the
  fixed lexicon, because readers will not decode them consistently.

### 5. Hedged first-person language on weak claims measurably improves user accuracy

Kim et al. (FAccT 2024; pre-registered, n=404, medical questions) found that a
first-person hedge ("I'm not sure, but…") on LLM answers "decrease[d] participants'
confidence in the system and tendency to agree with the system's answers, while
increasing participants' accuracy" — i.e. it reduced *over*reliance exactly where
reliance was unwarranted. Microsoft's HAX Guideline 2 codifies the same as pattern
2A "match linguistic precision to performance" (hedged wording rather than absolute
claims) and 2D "provide low performance alerts". General uncertainty phrasing
("It's not clear…") was weaker than first-person phrasing.

- Proven in: [Kim et al. 2024](https://dl.acm.org/doi/10.1145/3630106.3658941) ([arXiv](https://ar5iv.labs.arxiv.org/html/2405.00623)), [Microsoft HAX Guideline 2](https://www.microsoft.com/en-us/haxtoolkit/guideline/make-clear-how-well-the-system-can-do-what-it-can-do/) (fetched in full).
- Good for: the **inferred** and **default-proposed** classes in #10. The system's
  prose voice should hedge in the sentence itself, not only in a badge — the badge
  and the wording must agree.

### 6. Refusal guardrails: when evidence is thin, do not render the artefact at all

The Consensus Meter is the best worked example of a categorical confidence artefact
with explicit guardrails: it answers yes/no questions with a Yes/Possibly/Mixed/No
meter, but **requires at least 5 relevant papers to fire**, applies relevancy and
classifier-confidence thresholds ("excluding results… when the classifier model
isn't confident enough in which direction an answer leans"), and shows every
underlying paper below the meter with its classification tag, colour-coded to match.
Its published limitations are equally instructive: it counts papers "without
weighing study design, sample size, or journal quality" — a warning against
aggregate meters that hide quality variance.

- Proven in: [Consensus Meter help article](https://help.consensus.app/en/articles/10069920-the-consensus-meter), [guardrails and limitations post](https://consensus.app/home/blog/consensus-meter/), [Meter 2.0](https://consensus.app/home/blog/new-consensus-meter/).
- Good for: #10's founding rule ("the system proposes defaults and records
  assumptions — it never presents a guess as fact"). The UI equivalent: below a
  minimum evidence threshold the snapshot shows "not enough evidence to say",
  never a low-confidence verdict styled like a verdict.

### 7. "How we got this" expanders — derivation on demand, grounded in evidence, not model rationalisation

Elicit attaches, to every extracted value, a supporting quote *and* an explanation,
behind a click; Google Search's AI features expose hover previews naming the source
before you commit to it; PAIR frames explanations as answering "what should the
user's action be under this level of confidence". NN/g adds the crucial caveat:
step-by-step reasoning walkthroughs "are rationalizations generated after the fact,
rather than faithful representations of how the model arrived at an answer" — so
the expander must contain *retrievable evidence and recorded assumptions*, not a
generated justification.

- Proven in: [Elicit](https://intuitionlabs.ai/articles/elicit-data-extraction-clinical-papers), [PAIR guidebook](https://pair.withgoogle.com/chapter/explainability-trust/), caveat in [NN/g Explainable AI in Chat Interfaces](https://www.nngroup.com/articles/explainable-ai/).
- Good for: the #10 assumptions register. An assumption callout should expand to
  the recorded "why we assumed this, what would change it" — written at the moment
  the assumption was made, not regenerated on demand. That record is also what lets
  an assumption be upgraded or retired later without archaeology.

### 8. Design against the documented failure modes

1. **Citations inflate trust while going unread.** NN/g: "people rarely click
   citation links… because the citations appear trustworthy, this perception alone
   strengthens confidence in the output", and citations are sometimes hallucinated
   or do not support the claim ([NN/g](https://www.nngroup.com/articles/ai-chatbots-discourage-error-checking/)).
   He & Liu's 394-participant experiment across four citation layouts (collapsible
   list, hover cards, footer list, inline) found presentation significantly changed
   engagement and downstream knowledge/agreement — high-visibility citations drove
   more source hovering ([arXiv 2512.12207](https://arxiv.org/abs/2512.12207)).
   Implication for #22: a source chip is a *trust signal* whether or not it is
   checked; the prototype should test whether founders can distinguish "labelled"
   from "verified".
2. **Blanket disclaimers do not work.** Google's "AI responses may include
   mistakes" line under AI Overviews is the canonical buried caveat; NN/g notes
   chat UIs "rarely acknowledge that LLM outputs might not be entirely accurate"
   and nudge users onward ([Google support](https://support.google.com/websearch/answer/14901683), [NN/g](https://www.nngroup.com/articles/ai-chatbots-discourage-error-checking/)).
   Caveats must live **on the claim**, not in a footer.
3. **Overprecise single numbers without a reference class are misread.**
   Gigerenzer's "30% chance of rain" studies: the public reads the same number as
   30% of the area, 30% of the time, or 3-in-10 days like tomorrow; the fix is to
   state the reference class ([Gigerenzer et al. 2005](https://onlinelibrary.wiley.com/doi/10.1111/j.1539-6924.2005.00608.x)).
   A "72% confidence" badge on a strategy claim is strictly worse than a tier,
   because there is no reference class a founder could even ask about.
4. **Uncalibrated numeric confidence misleads.** Zhang, Liao & Bellamy (FAT* 2020)
   showed confidence scores can support trust calibration only case-by-case, and
   "confidence scores are not always well calibrated in ML classifiers"; local
   explanations failed to create a perceivable calibration effect ([ACM](https://dl.acm.org/doi/10.1145/3351095.3372852), [arXiv 2001.02114](https://arxiv.org/pdf/2001.02114)).
   Do not display numbers you cannot calibrate.
5. **Hard boundaries create containment effects.** Hurricane cone-of-uncertainty
   studies (Padilla et al.): people evacuate inside the cone and relax just outside
   it, with sharp cutoffs over short distances — a visual boundary is read as a
   risk boundary ([CSU study](https://natsci.source.colostate.edu/no-more-cone-psychology-researchers-offer-better-tool-for-visualizing-hurricane-danger/), [NOAA literature review](https://www.aoml.noaa.gov/general/lib/lib1/nhclib/Bibliographies/Cone%20of%20Uncertainty%20Literature%20Review_4_10_19%20(1)%20(1).pdf)).
   Confidence *tiers* inherit this risk: a claim one notch above the "unverified"
   line will be read as safe. #22 should test the boundary reading explicitly.
6. **Frequency framings beat abstract probability for lay decisions.** "When (ish)
   is my bus?" and the CHI 2018 follow-up: quantile dotplots (discrete "3 out of
   10 dots" displays) produced measurably better everyday decisions than density
   or interval displays ([CHI 2016](https://dl.acm.org/doi/10.1145/2858036.2858558), [CHI 2018](https://dl.acm.org/doi/10.1145/3173574.3173718)).
   Where the workspace ever needs to show a distributional claim, use counts
   ("in 7 of 10 comparable launches…"), not percentages.

### Mapping to #10 and #22 (synthesis, not source-backed)

- The five provenance classes in #10 (founder-supplied / mined verbatim / inferred /
  default-proposed / unverified) match the industry pattern of **provenance chips at
  claim level** (pattern 1) — but only *mined verbatim* and *founder-supplied* can
  carry quote-anchored evidence (pattern 2); *inferred* and *default-proposed* need
  the hedged voice (pattern 5) plus the "how we got this" expander (pattern 7);
  *unverified* is the refusal tier (pattern 6): render it as an open question, not
  a dimmed fact.
- Confidence tiers (pattern 3) and provenance classes are different axes and should
  not be conflated: a founder-supplied claim can still be low-confidence evidence.
  UpToDate's two-axis grade is the proven precedent for keeping them separate but
  co-displayed.
- For #22's "read without explanation" test, the misreadings the literature predicts
  are: citation-halo (labels read as verification), boundary containment (tier n+1
  read as safe), regressive reading of verbal labels, and disclaimers going unseen.
  Each is a cheap, specific prototype probe.

---

## Survey detail

### A. Citation UI in AI answer/search engines

**Perplexity.** Answers carry numbered inline citations; citations are assigned
during generation rather than retrofitted, and roughly 3–4 of ~10 consulted pages
earn a citation ([Perplexity help centre](https://www.perplexity.ai/help-center/en/articles/10352895-how-does-perplexity-work), [ZipTie analysis](https://ziptie.dev/blog/how-perplexity-ai-answers-work/)).
Third-party teardowns describe the current UI as: a horizontal source-card strip
above the answer (favicon, title, number), numbered chips at sentence ends with
hover previews (domain, title, excerpt), and a sources tab with full cards —
numbering consistent between chips and panel ([AI UX Playground](https://aiuxplayground.com/teardowns/perplexity/citations/), [LLM Pulse](https://llmpulse.ai/blog/how-perplexity-works/)) [UNVERIFIED — vendor help pages unreachable from this environment; details from teardowns].

**Google AI Overviews / AI Mode.** Inline links in the overview text, a right-hand
source panel on desktop, and hover pop-ups showing the site name or page title;
Google's stated design goal is directing users to the web ([Google blog](https://blog.google/products-and-platforms/products/search/explore-web-generative-ai-search/), [9to5Google](https://9to5google.com/2026/05/06/google-ai-mode-overviews-direct-links/)).
Eligibility as a supporting link requires only normal Search indexing ([Google Search Central](https://developers.google.com/search/docs/appearance/ai-features)).
The feature carries the disclaimer "AI responses may include mistakes"
([Google support](https://support.google.com/websearch/answer/14901683)) — widely
criticised as inadequate relative to error volume ([The Deep View](https://www.thedeepview.com/articles/why-google-ai-overviews-expose-ai-s-biggest-problem)).

**Bing / Microsoft Copilot.** Footnote-style numbered citations in the answer, with
"Show all" opening a right-hand reference panel; Microsoft has experimented with
inline links and side-cards showing supporting evidence alongside the text, and with
shrinking the clickable area to the citation marker alone ([EAX Media](https://eaxmedia.com/bing-copilot-inline-citations-sidecards-update/), [WindowsForum](https://windowsforum.com/threads/bing-copilot-search-tests-smaller-clickable-citations-impact-on-web-traffic-and-seo.415491/)) [UNVERIFIED — Microsoft's own UI documentation unreachable; details from trade coverage].

**ChatGPT search.** Inline citations with hover detail; a "Sources" button beneath
the response opens a sidebar with all references; image results link to their source
([OpenAI help centre](https://help.openai.com/en/articles/9237897-chatgpt-search)).

**Claude / Anthropic Citations API** (fetched in full). Citations "return the exact
passages that support each claim, so you can verify answers and surface sources to
your users"; each citation includes `cited_text` plus precise document location, and
citations are structurally generated rather than prompted. Web-search responses
always carry citations ([Citations docs](https://platform.claude.com/docs/en/build-with-claude/citations), [web search announcement](https://claude.com/blog/web-search-api), [Citations announcement](https://claude.com/blog/introducing-citations-api)).

### B. Confidence and provenance labelling in research/analysis tools

**Elicit.** Extraction tables where every AI-filled cell is clickable to reveal the
supporting quote shown in the context of the paper, plus an explanation; low-
confidence answers are visually flagged so users can rephrase or verify; models are
constrained to report what the abstract actually says ([Elicit blog](https://elicit.com/blog/living-documents-ai-ux), [IntuitionLabs guide](https://intuitionlabs.ai/articles/elicit-data-extraction-clinical-papers), [Elicit limitations](https://support.elicit.com/en/articles/549569)).
Elicit publishes its own accuracy figures and limitations openly (abstract-only
access for many papers; no risk-of-bias appraisal) ([Deakin evaluation](https://deakin.libguides.com/AI-Evaluations/Elicit)).

**Consensus.** The Consensus Meter classifies the top ~20 papers on a yes/no
question into Yes/Possibly/Mixed/No; ≥5 relevant papers required; relevancy and
classifier-confidence thresholding; results are word-for-word quotes; each paper is
tagged and colour-coded to its classification; a "Consensus Snapshot" table adds
per-position summaries and study metadata (recency, methods, journals, citations)
([help centre](https://help.consensus.app/en/articles/10069920-the-consensus-meter), [guardrails post](https://consensus.app/home/blog/consensus-meter/), [how it works](https://help.consensus.app/en/articles/9922673-how-consensus-works)).
Known limitation: papers are counted, not weighted by quality ([guardrails post](https://consensus.app/home/blog/consensus-meter/)).

**Medical decision tools.** GRADE: certainty rated High/Moderate/Low/Very-low from
named criteria (risk of bias, inconsistency, indirectness, imprecision, publication
bias) ([CDC ACIP GRADE handbook](https://www.cdc.gov/acip-grade-handbook/hcp/chapter-7-grade-criteria-determining-certainty-of-evidence/index.html)).
UpToDate: two-axis grades 1A–2C — strength of recommendation (1 strong, 2 weak) ×
quality of evidence (A/B/C) — "from the very strong (benefit/risk tradeoff
unequivocal, high quality evidence, 1A) to the very weak" ([UpToDate grading guide](https://www.wolterskluwer.com/en/solutions/uptodate/policies-legal/grading-guide)).
USPSTF letter grades A–D plus I ("insufficient evidence") — a refusal tier in
production use ([USPSTF](https://www.uspreventiveservicestaskforce.org/uspstf/about-uspstf/methods-and-processes/grade-definitions)).

**Financial decision tools.** Morningstar separates the backward-looking
quantitative star rating from the forward-looking qualitative analyst rating
(Gold/Silver/Bronze/Neutral/Negative), explicitly to reduce complexity and increase
transparency for investors ([Morningstar ratings](https://www.morningstar.com/company/ratings)).

### C. Published UX guidance and academic research

**Microsoft HAX Toolkit, Guideline 2** ("Make clear how well the system can do what
it can do"; fetched in full): four patterns — 2A match linguistic precision to
performance; 2B match numerical precision to performance; 2C report system
performance information; 2D provide low-performance alerts. Rationale: users
misjudge AI reliability in both directions (automation bias vs algorithm aversion)
([HAX Guideline 2](https://www.microsoft.com/en-us/haxtoolkit/guideline/make-clear-how-well-the-system-can-do-what-it-can-do/)).

**Google PAIR People + AI Guidebook** (Explainability + Trust): only display
confidence if it demonstrably improves decisions; options are categorical buckets
(with an action per bucket), N-best alternatives, or numeric — and numeric is
hardest for users; test displays early with the real audience
([PAIR guidebook](https://pair.withgoogle.com/chapter/explainability-trust/), [Codelab companion](https://codelabs.developers.google.com/codelabs/pair-guidebook)).

**Nielsen Norman Group.** Two findings pairs: (i) users rarely click citations, yet
citations' presence alone increases confidence in the output — including when
citations are hallucinated or unsupportive; (ii) chat UIs discourage error checking
via the halo effect and move-on prompting; remedy is passage-level deep links and
previews ([Explainable AI in Chat Interfaces](https://www.nngroup.com/articles/explainable-ai/), [AI Chatbots Discourage Error Checking](https://www.nngroup.com/articles/ai-chatbots-discourage-error-checking/)).

**Uncertainty-communication research.**
- van der Bles et al. 2019: framework of uncertainty objects (facts, numbers,
  science) and a nine-expression scale of direct uncertainty ([R. Soc. Open Sci.](https://royalsocietypublishing.org/doi/10.1098/rsos.181870)).
- van der Bles et al. 2020: numeric-range uncertainty barely reduces trust; vague
  verbal uncertainty reduces perceived reliability more (5 experiments, n=5,780)
  ([PNAS](https://www.pnas.org/doi/abs/10.1073/pnas.1913678117)).
- Budescu et al.: IPCC verbal probability terms read regressively toward 50%;
  verbal+numeric format raises consistency 27%→40% ([2009 study](https://moodle2.units.it/pluginfile.php/232175/mod_resource/content/1/Budescu,%20Broomell,%20Por%20(2009).pdf), [24-country study](https://www.researchgate.net/publication/275118595_The_Interpretation_of_IPCC_Probabilistic_Statements_Around_the_World)); IPCC calibrated scale itself: [AR5 guidance note](https://www.ipcc.ch/site/assets/uploads/2017/08/AR5_Uncertainty_Guidance_Note.pdf).
- Kim et al. FAccT 2024: first-person hedges reduce overreliance and improve user
  accuracy (n=404) ([ACM](https://dl.acm.org/doi/10.1145/3630106.3658941)).
- Zhang, Liao & Bellamy FAT* 2020: confidence scores support calibration only when
  themselves calibrated; local explanations did not help ([ACM](https://dl.acm.org/doi/10.1145/3351095.3372852)).
- Kay et al. CHI 2016 / Fernandes et al. CHI 2018: quantile dotplots (frequency
  framing) beat abstract probability displays for lay transit decisions
  ([CHI 2016](https://dl.acm.org/doi/10.1145/2858036.2858558), [CHI 2018](https://dl.acm.org/doi/10.1145/3173574.3173718)).
- Gigerenzer et al. 2005: single-event probabilities need explicit reference
  classes ([Risk Analysis](https://onlinelibrary.wiley.com/doi/10.1111/j.1539-6924.2005.00608.x)).
- Padilla et al. / CSU / U. Miami: cone-of-uncertainty containment effect — visual
  boundaries read as risk boundaries ([CSU](https://natsci.source.colostate.edu/no-more-cone-psychology-researchers-offer-better-tool-for-visualizing-hurricane-danger/), [NOAA review](https://www.aoml.noaa.gov/general/lib/lib1/nhclib/Bibliographies/Cone%20of%20Uncertainty%20Literature%20Review_4_10_19%20(1)%20(1).pdf), [U. Miami](https://news.miami.edu/stories/2024/02/cone-of-uncertainty-graphic-to-feature-more-information.html)).
- He & Liu 2025: four citation-presentation layouts compared experimentally (n=394);
  visibility changes attention and downstream agreement ([arXiv 2512.12207](https://arxiv.org/abs/2512.12207)).
- Full Fact / Winton Centre briefing on communicating uncertainty to the public
  ([PDF](https://fullfact.org/media/uploads/en-communicating-uncertainty.pdf))
  [UNVERIFIED — PDF unreachable from this environment; listed as a known primary
  guidance document for follow-up].

### D. What fails — condensed

| Anti-pattern | Evidence | Fix |
|---|---|---|
| Citations as decoration (unclicked, trust-inflating) | [NN/g](https://www.nngroup.com/articles/explainable-ai/) | Quote-anchored previews; distinguish "labelled" from "verified" |
| Blanket footer disclaimers | [Google AI Overviews](https://support.google.com/websearch/answer/14901683), [criticism](https://www.thedeepview.com/articles/why-google-ai-overviews-expose-ai-s-biggest-problem) | Claim-level caveats in the claim's own wording |
| Overprecise percentages, no reference class | [Gigerenzer 2005](https://onlinelibrary.wiley.com/doi/10.1111/j.1539-6924.2005.00608.x) | Tiers, or counts with an explicit reference class |
| Uncalibrated numeric confidence | [Zhang et al. 2020](https://dl.acm.org/doi/10.1145/3351095.3372852) | Show numbers only if calibrated; otherwise categories or N-best |
| Free-floating verbal probability words | [Budescu](https://www.researchgate.net/publication/275118595_The_Interpretation_of_IPCC_Probabilistic_Statements_Around_the_World) | Tiny fixed lexicon, each term anchored to a defined meaning |
| Hard tier boundaries read as safety lines | [Padilla et al.](https://natsci.source.colostate.edu/no-more-cone-psychology-researchers-offer-better-tool-for-visualizing-hurricane-danger/) | Test boundary readings in #22; style tiers as bands, not verdicts |
| Aggregate meters hiding quality variance | [Consensus limitations](https://consensus.app/home/blog/consensus-meter/) | Show the underlying items with per-item tags below any rollup |
| Post-hoc reasoning presented as derivation | [NN/g](https://www.nngroup.com/articles/explainable-ai/) | Expanders contain recorded evidence and assumptions, not regenerated justifications |

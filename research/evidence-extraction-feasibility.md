Context: https://github.com/HannahMooreHM/Founder-Creative-Strategy-Space/issues/5

# Evidence extraction: feasibility and cost

Research for the intake "search cascade": (1) brand-name pass across review platforms, (2) category-voice pass, (3) fetching every external site the client links to, (4) competitor review pages.

**Verification note.** This environment's egress policy blocked direct fetching of most platform domains (reddit.com, developers.google.com, facebook.com, linkedin.com, tiktok.com, g2.com, capterra.com, trustpilot.com and others returned proxy-level 403s). The Google Maps Platform Terms were fetched directly and are quoted verbatim. All other ToS/API claims cite the primary URL and were corroborated through search-result extracts of those primary pages; they are reliable in substance but exact wording should be re-checked against the live page before quoting in client-facing material. Items that could not be corroborated at all are marked [UNVERIFIED]. Estimates are labelled as estimates.

---

## Decisive summary

**1. The compliant automated surface is narrower than the cascade assumes.** What can be extracted automatically today, within each platform's own terms:

- **Client's own website + every site it links to** — fully automatable via plain HTTP for the large majority of small-business sites. This is the safest and richest automated layer.
- **Google reviews** — two compliant routes only: (a) Places API Place Details returns a **maximum of five reviews per place** and Google's terms prohibit storing them; (b) with the **client's own authorisation**, the Google Business Profile API returns **all** reviews for their listing. Route (b) is the only way to get a client's full Google review corpus legitimately.
- **Facebook Page ratings** — full list via Graph API `/{page-id}/ratings`, but only with a Page access token, i.e. client consent.
- **Trustpilot** — API access requires a Trustpilot **Business account** and API key; the practical route is the client's own account (or their CSV export). Site scraping is expressly prohibited.
- **Reddit** — readable via the official Data API; free tier is **non-commercial only** (~100 queries/min per OAuth client); commercial use requires Reddit's prior approval and a paid agreement. A paid productised service is commercial use.
- **Practically blocked for automation**: LinkedIn (contract + robots.txt prohibition, aggressive enforcement), Instagram/Facebook public pages (ToS §3.2.3 bans automated collection; login wall after ~6–12 posts), TikTok (ToS ban + one of the strongest anti-bot stacks; Research API is academic-only), G2/Capterra (ToS ban + DataDome/Cloudflare-class defences; official APIs are for vendors/syndication partners, not third-party mining).

**2. The design consequence for intake (#11): build the intake around client-granted access, not scraping.** The one pattern that converts "blocked" into "fully extractable" is asking the client to connect or export their own accounts: Google Business Profile, Facebook Page, Trustpilot Business, plus screenshots/exports of anything else. Competitor review pages (cascade step 4) have **no consent route**; the compliant method is a human reading public pages and taking notes, optionally AI-assisted summarisation of what the human collected.

**3. For autonomy (#12): steps 1 and 4 of the cascade cannot be safely fully autonomous.** The brand-name pass and competitor-review pass hit ToS-prohibited or anti-bot-protected surfaces (G2, Capterra, Trustpilot without client credentials, Instagram, LinkedIn, TikTok). A concierge human-in-the-loop model is not just cheaper to build — it is the only version that does not depend on breaching platform terms. Steps 2 and 3 (open-web category voice, client's outbound links) can be autonomous.

**4. For failure states (#25): "no evidence found" is the modal outcome for very small brands, not an edge case.** Roughly a third of SMBs even have a Google Business Profile (secondary reporting of BrightLocal data; estimate), and pre-launch or sub-£100k founders typically have zero Trustpilot/G2/Reddit brand mentions. The intake must treat an empty brand-name pass as an expected, designed-for state (fall back to category-voice evidence), not an error.

**5. Cost (estimates):** marginal tooling cost per intake is trivial — under ~£5 in API/LLM spend. The real cost is labour: **~2–4 hours per intake** for a concierge version on a typical small brand, **~4–8 hours** for a review-rich brand. Reddit commercial API access is the one large fixed cost if ever automated at product scale (reported ~$0.24/1,000 calls with enterprise minimums; small-scale concierge use sidesteps this by keeping human reading in the loop).

---

## Per-source detail

### Founder's own website (and every external site it links to — cascade step 3)

- **Feasibility: high.** Plain HTTP fetch + HTML parsing works for most small-business sites (WordPress, Squarespace, Wix, Shopify all serve server-rendered or hydration-friendly HTML). Link extraction to build the outbound-link list is trivial.
- **Failure modes:** JS-only rendering (single-page apps whose body is empty without a headless browser) — my estimate ~10–20% of founder sites, fixable with headless rendering; hard anti-bot on the founder's own site is rare. Outbound links rot: expect a minority of dead/redirected links per site (estimate).
- **Legal:** fetching the client's own site with their consent is unproblematic. For third-party sites the client links to, respect robots.txt (RFC 9309 makes it a widely-honoured convention, not law) and each site's terms; one-off fetching of public pages for internal analysis is low-risk, per the hiQ line of cases below.

### Google reviews / Places

- **Places API (New), Place Details:** the `reviews` field returns **up to five reviews per place** ([Place Details docs](https://developers.google.com/maps/documentation/places/web-service/place-details); the JS API Places library states "an array of up to five reviews" — [docs](https://developers.google.com/maps/documentation/javascript/legacy/places)). Reviews/ratings ("atmosphere" data) bill at the **Enterprise SKU, ~US$20 per 1,000 requests** with 1,000 free calls/month ([pricing](https://developers.google.com/maps/billing-and-pricing/pricing); corroborated by secondary pricing guides). So an API lookup costs ~2 pence per business — but yields only 5 reviews.
- **Google Maps Platform Terms, §3.2.3 (fetched directly, verbatim):** "(a) *No Scraping.* Customer will not export, extract, or otherwise scrape Google Maps Content for use outside the Services. For example, Customer will not: (i) pre-fetch, index, store, reshare, or rehost Google Maps Content outside the services; … (iii) **copy and save business names, addresses, or user reviews**; …" and "(b) *No Caching.* Customer will not cache Google Maps Content except as expressly permitted…" ([terms](https://cloud.google.com/maps-platform/terms)). So even the 5 API reviews cannot be stored in a client dossier under these terms — display-and-discard only.
- **The compliant full-corpus route:** Google Business Profile API `accounts.locations.reviews.list` returns **all reviews, paginated, with average rating and total count** — but only for a **verified location the authenticated account manages**, i.e. with the client's OAuth consent ([review data guide](https://developers.google.com/my-business/content/review-data); [reviews.list reference](https://developers.google.com/my-business/reference/rest/v4/accounts.locations.reviews/list)). This is the recommended intake mechanism.
- **Scraping Google Maps directly:** prohibited by the terms above; Google's serving stack is heavily bot-protected. Not viable.

### Trustpilot

- **API:** requires a **Trustpilot for Business account**; API keys are created in their Developer Portal, and "public" endpoints still require the API key (Client ID), with OAuth for private endpoints ([authentication overview](https://developers.trustpilot.com/authentication); [How to use Trustpilot APIs](https://help.trustpilot.com/s/article/How-to-use-Trustpilot-APIs); [Business Units API (public)](https://developers.trustpilot.com/business-units-api-(public)/)). Practical route: the client's own business account, or a manual export.
- **ToS:** Trustpilot's consumer Terms of Use prohibit accessing or collecting platform content "by any means (automated or otherwise)" beyond normal use without approval, and expressly prohibit text mining, data mining and web scraping, including for AI training; Trustpilot states it blocks and, where appropriate, litigates against scrapers ([Terms of Use for Consumers](https://legal.trustpilot.com/for-reviewers/terms-of-use-for-consumers); [Action we take](https://legal.trustpilot.com/for-everyone/action-we-take)).
- **Feasibility:** reading a brand's Trustpilot page manually is fine; automated scraping is contractually barred. Small brands frequently have no Trustpilot profile at all (estimate; presence skews to e-commerce/consumer services).

### Reddit (dominant source for cascade step 2, category voice)

- **Official Data API:** free for **non-commercial** use within ~**100 queries per minute per OAuth client**; **commercial use requires prior approval and a paid agreement** (reported at ~$0.24/1,000 calls with high-volume enterprise tiers). Primary sources: [Data API Terms](https://www.redditinc.com/policies/data-api-terms) and the [Data API Wiki](https://support.reddithelp.com/hc/en-us/articles/16160319875092) — both fetch-blocked in this environment; figures corroborated by multiple secondary sources ([SocialCrawl](https://www.socialcrawl.dev/blog/reddit-data-api-2026), [Prowlo](https://prowlo.com/blog/reddit-api-pricing)). Reports that self-serve OAuth registration closed in late 2025, making all new API access approval-gated, are [UNVERIFIED] against Reddit's own pages.
- **robots.txt / Public Content Policy:** since mid-2024 Reddit's robots.txt disallows essentially all crawlers, directing automated agents to its [Public Content Policy](https://www.redditinc.com/policies/public-content-policy) and licensing ([TechCrunch report of Reddit's announcement](https://techcrunch.com/2024/06/25/reddits-upcoming-changes-attempt-to-safeguard-the-platform-against-ai-crawlers)).
- **Feasibility:** a human searching Reddit in a browser and quoting what they find is unrestricted. Automated mining for a paid service sits in commercial-approval territory. For concierge volume (a handful of brands/week), manual search + AI summarisation of copied threads is compliant and cheap.

### Instagram / Facebook (Meta)

- **ToS:** Meta's Terms of Service §3.2.3: "You may not access or collect data from our Products using automated means (without our prior permission) or attempt to access data you do not have permission to access, regardless of whether such automated access or collection is undertaken while logged-in to a Facebook account" ([Meta Terms](https://www.facebook.com/terms); see also the [Automated Data Collection Terms](https://www.facebook.com/legal/automated_data_collection_terms)).
- **Practical access:** Instagram's login wall now blocks anonymous browsing after roughly 6–12 posts; stories, reels and most comments require login (secondary reporting; estimate). So even "just look at the public profile" is partially gated.
- **Official APIs:** the Instagram Platform API serves professional accounts the app user manages; **Business Discovery** allows limited read of *another* professional account's public metadata and media (follower count, media count, published media) via a Facebook-Login-authenticated business app — no access to that account's comments beyond media objects surfaced this way ([Business Discovery docs](https://developers.facebook.com/docs/instagram-api/business-discovery)). Facebook Page ratings/reviews are readable via Graph API `/{page-id}/ratings` **with a Page access token carrying `pages_read_user_content`** — i.e. client consent ([Graph API docs](https://developers.facebook.com/docs/graph-api/reference/insights/)). oEmbed provides embed HTML for public posts; secondary sources report Meta removed the token/App Review requirement in June 2026 [UNVERIFIED against Meta's own docs] ([oEmbed docs](https://developers.facebook.com/docs/instagram-platform/oembed/)).
- **Feasibility verdict:** manual viewing + client-provided screenshots/exports, plus Page-token reads for the client's own Facebook Page. No compliant automated route to mining third-party Instagram comments.

### LinkedIn

- **ToS:** User Agreement §8.2 prohibits developing or using "software, devices, scripts, robots or any other means or processes (including crawlers, browser plugins and add-ons or any other technology) to scrape the Services or otherwise copy profiles and other data from the Services" and using bots or automated methods to access the Services ([User Agreement](https://www.linkedin.com/legal/user-agreement)). [robots.txt](https://www.linkedin.com/robots.txt) states: "The use of robots or other automated means to access LinkedIn without the express permission of LinkedIn is strictly prohibited."
- **Legal context:** hiQ v LinkedIn — the Ninth Circuit held scraping public data likely does not violate the US CFAA (2022), but LinkedIn **won on breach of contract** at district level and hiQ settled with a permanent injunction and $500k damages ([Proskauer summary](https://newmedialaw.proskauer.com/2022/12/08/hiq-and-linkedin-reach-proposed-settlement-in-landmark-scraping-case/); [Jenner client alert](https://www.jenner.com/en/news-insights/publications/client-alert-data-scraping-in-hiq-v-linkedin-the-ninth-circuit-reaffirms-narrow-interpretation-of-cfaa)). Lesson: "not criminal" ≠ "not a breach".
- **Feasibility verdict:** manual viewing only; the client can export their own profile/company page content. No compliant automation.

### TikTok

- **ToS:** prohibits automated scripts/data collection (TikTok [Terms of Service](https://www.tiktok.com/legal/page/us/terms-of-service/en); corroborated by secondary sources).
- **Research API:** restricted to vetted **academic/non-profit researchers** in eligible regions (US and parts of Europe), explicitly non-commercial ([Research API](https://developers.tiktok.com/products/research-api/); [FAQ](https://developers.tiktok.com/doc/research-api-faq)). Not available to a commercial strategy service.
- **Practical:** public web profiles are viewable without login, but TikTok runs among the strongest anti-bot stacks (device/TLS fingerprinting, behavioural analysis, signatures) — naive scraping fails quickly (secondary: [ScrapeOps](https://scrapeops.io/websites/tiktok/), [Scrapfly](https://scrapfly.io/blog/posts/how-to-scrape-tiktok-python-json)).
- **Verdict:** manual viewing + client exports only.

### G2 / Capterra (and competitor review pages generally — cascade step 4)

- **G2 ToS:** prohibits accessing, collecting, copying, scraping, harvesting, caching, indexing or extracting any content or data — expressly including **user reviews** — by automated means, "whether or not such content is publicly accessible", without written consent ([G2 Terms of Use](https://legal.g2.com/terms-of-use)). G2's official APIs exist but are for **vendors and syndication partners** under licence, not third-party mining ([G2 review syndication docs](https://documentation.g2.com/partners/docs/get-started-with-g2-review-syndication); [G2 API](https://data.g2.com/api/docs)).
- **Capterra/Gartner:** Capterra's User Terms prohibit automated means/data scraping to access, query, download or collect content ([User Terms](https://www.capterra.com/legal/terms-of-use/)); Gartner Peer Insights' Rules of Engagement likewise prohibit unauthorised robots/spiders/scrapers ([Rules of Engagement](https://www.gartner.com/reviews/faq/rules-of-engagement)).
- **Anti-bot:** both sites sit behind top-tier bot protection; scraping-industry benchmarks class G2 and Capterra among the hardest mainstream targets (secondary: [ScrapeOps G2 guide](https://scrapeops.io/websites/g2/)).
- **TripAdvisor:** the official Content API returns location details plus **up to 5 of the most recent reviews and 5 photos per location**, budget-based daily limits, 50 QPS ([Location Reviews reference](https://tripadvisor-content-api.readme.io/reference/getlocationreviews); [rate limits](https://tripadvisor-content-api.readme.io/reference/rate-limits)). Same pattern as Google: an official taster, not a corpus.
- **Verdict for competitor pages:** there is **no consent route** for competitors' reviews. Compliant method = human reads the public pages, takes structured notes; AI summarises the human's notes. Automated bulk extraction is both contractually barred and technically contested.
- **Legal context for public-page scraping generally:** in Meta v Bright Data (N.D. Cal. 2024) Meta lost its contract claim over **logged-off** scraping of public pages, a counterweight to hiQ — the law is unsettled and platform-specific; contract risk is real whenever an account/login is involved ([Farella Braun + Martel analysis](https://www.fbm.com/publications/major-decision-affects-law-of-scraping-and-online-data-collection-meta-platforms-v-bright-data/)).

---

## Effort and cost per intake (concierge + AI-assisted) — all estimates

| Step | Method | Time (est.) | Cash cost (est.) |
|---|---|---|---|
| Client-site + outbound-link fetch & summarise | Automated fetch + LLM summarise | 15–30 min review | pennies (LLM tokens) |
| Google reviews | Client connects GBP / exports; else Places lookup (5 reviews, display-only) | 15–45 min | ~£0.02/lookup; £0 with client consent |
| Trustpilot / Facebook ratings | Client account/API key or export | 15–30 min | £0 |
| Brand-name pass (Reddit, forums, social) | Manual search, copy-paste, LLM synthesis | 30–90 min | pennies |
| Category-voice pass | Manual + automated open-web search | 45–90 min | pennies |
| Competitor review pages | Human reads 2–4 competitors, structured notes | 45–120 min | £0 |
| **Total** | | **~2–4 h typical; 4–8 h review-rich** | **< £5/intake** |

At ~£30–60/h effective labour cost, that is roughly **£60–£250 of labour per intake** (estimate). The scaling ceiling is labour, not tooling; the one big step-change cost would be Reddit commercial API access if the service ever automates that layer at product scale.

## Failure modes and rough base rates

| Failure mode | Rough base rate | Basis |
|---|---|---|
| No Google review presence | High for very small/pre-launch brands: only ~35% of SMBs reported to have a Google Business Profile at all; local businesses that have one average ~39 reviews | Secondary reporting of BrightLocal research ([Google Reviews study](https://www.brightlocal.com/research/google-reviews-study/), [review statistics](https://www.brightlocal.com/resources/online-reviews-statistics/)); treat the 35% figure as indicative [estimate] |
| No Trustpilot/G2/Capterra presence | Very high for sub-£100k and service businesses (these platforms skew e-commerce and B2B SaaS) | My estimate — no primary statistic found |
| No Reddit/category-voice mentions of the brand | The norm for unknown brands; category-level voice almost always exists | My estimate |
| Client site unfetchable without JS rendering | ~10–20% of founder sites; recoverable with headless browser | My estimate |
| Blocked scraping / anti-bot on review platforms | Near-certain for automated attempts on G2, Capterra, TikTok, Instagram, LinkedIn | Platform ToS + scraping-industry benchmarks cited above |
| Client cannot or will not grant account access | Material minority — design the intake with an export/screenshot fallback | My estimate |

**Design implication:** the intake must ship with a defined "thin evidence" path — when the brand-name pass returns nothing (expected for the smallest clients), the deliverable leans on the category-voice pass and the client's own materials, and says so explicitly rather than failing.

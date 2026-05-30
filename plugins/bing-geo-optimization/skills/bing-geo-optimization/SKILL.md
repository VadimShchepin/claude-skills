---
name: bing-geo-optimization
description: >
  Optimize content to get cited by Microsoft Copilot and Bing's generative AI
  answers. Grounded in a real Bing Webmaster Tools AI citation export rather than
  generic GEO theory. Covers the empirically validated citation recipe
  (defined-jargon + named-tools + benchmark-numbers), how Bing's grounding /
  query fan-out works, how to read the AI Performance, AI Page Stats and AI
  Search Queries reports, the grounding-query reverse-engineering method, and
  IndexNow technical eligibility. Use when the user says "Bing", "Copilot",
  "Microsoft Copilot", "Bing Copilot", "Bing AI", "grounding queries", "Bing
  Webmaster Tools AI", "IndexNow", or wants to get cited specifically by Bing /
  Copilot. For Google AI Overviews use google-geo; for cross-platform GEO
  (ChatGPT, Perplexity, llms.txt) use seo-geo / ai-seo.
---

# Bing & Copilot GEO Optimization

Get content cited in Microsoft Copilot and Bing's AI answers. This skill is grounded
in a **real Bing Webmaster Tools AI citation export** (aiseo.hamburg, May 2026), not
third-party theory. Where it differs from generic GEO advice, it is because the data
showed what actually moved citations on this engine.

**What the data was:** three CSVs from Bing Webmaster Tools' AI Performance section,
covering Feb to late May 2026:
- `AIPerformanceOverviewStats` — daily `Citations` and `Cited Pages`.
- `AIPageStatsReport` — total `Citations` per URL.
- `AISearchQueriesReport` — `Grounding Query` strings and their citation counts.

One page (`/wissen/ki-sichtbarkeit-messen`) earned **248 of ~600 citations (~58%)**;
only 10 of 42 articles got any citations at all. The rest of this skill explains why,
and how to reproduce it.

**Choosing between skills:** for Google's AI features (AI Overviews, AI Mode) use
`google-geo`. For cross-platform GEO that also covers ChatGPT, Perplexity, llms.txt and
brand-mention strategy, use `seo-geo` or `ai-seo`. This skill is **Bing / Copilot
specific**. See `references/skill-comparison.md`.

---

## Core premise: Copilot grounds on the Bing index via query fan-out

Microsoft Copilot answers are produced by **retrieval-augmented generation over the Bing
index**. A user prompt is not searched verbatim. Copilot rewrites it into one or more
**grounding queries** (a query fan-out), retrieves candidate passages for each, and the
model cites the passages it actually used. Implications:

- To be cited, a page must first be **in the Bing index** and retrievable for a grounding
  query. Bing SEO is the floor; GEO is the ceiling.
- The grounding queries are **machine-generated and keyword-dense**. They bundle the
  jargon of a topic into one long string (see below). The page that most completely and
  explicitly matches that bundle wins the citation.
- Bing Webmaster Tools **exposes the grounding queries to you**. This is the single
  biggest advantage Bing has over every other AI engine: you can read the retriever's
  own words and optimize directly against them.

---

## The validated recipe (what wins Bing citations)

In the export, the winning page was the **only** page that combined all of the following
on a single URL. Pages that had rich structure (TL;DR, FAQ, tables) but lacked these
earned **zero** citations, even when a grounding query literally asked for their topic.
Structure is necessary but not sufficient. **Term density is the moat.**

### 1. Define the jargon as glossable units
Each key term gets its own heading, followed by a one-sentence definition and a number or
formula. Copilot's grounding queries are built from these exact terms, so the page must
contain them explicitly, defined, not paraphrased away.

> **Share of Voice in KI-Antworten** misst, wie oft deine Marke im Vergleich zu
> Wettbewerbern in KI-Antworten zitiert wird. Bei 100 Prompts 12-mal zitiert = 12 % Share
> of Voice.

This single mechanic (domain-specific terminology + unique vocabulary) is consistent with
the Princeton GEO finding that technical terms (+18%) and unique vocabulary (+15%) lift AI
visibility. On Bing it is decisive because the grounding query *is* the jargon bundle.

### 2. Name real, branded tools and entities
Not "monitoring tools" but **Ahrefs Brand Radar, Semrush AI Visibility, GA4, GoAccess,
GPTBot, OAI-SearchBot, PerplexityBot**. Proper nouns are retrievable anchors. Generic
category words are not.

### 3. Attach a number to every claim
A benchmark, range, or price on each metric: "20-40 % Citation Rate in der Nische",
"15-25 % MoM", "ab 99 $/Monat". Statistics carried the citations (consistent with +37%
for statistics, +40% for cited sources in the Princeton study). A page of adjectives gets
ignored; a page of numbers gets quoted.

### 4. Structure for passage extraction
- A **TL;DR / definition box** in the first screen.
- A **named, numbered framework** ("Die 4 Messebenen", "5 KPIs").
- **FAQ phrased as literal user questions**, each answered self-containedly in 40-80 words.
- Short, chunked answer blocks (one idea each), not walls of prose.
- A **Quellen / sources** block with named, dated references.

### 5. Frame against the displaced thing
The grounding queries included "Keyword Ranking **ersetzen**" (replace keyword ranking).
Pages that explicitly contrast the new concept with the old one ("GSC ist blind für
KI-Traffic", "ersetzt klassisches Ranking-Reporting") match comparison-shaped grounding
queries.

**One-line recipe:** one URL that *defines the topic's jargon, names the real tools, puts a
number on every metric, and chunks it for extraction* will dominate that topic's grounding
queries on Bing.

---

## The grounding-query reverse-engineering method

This is the workflow that makes Bing optimization measurable instead of speculative.

1. **Export the AI Search Queries report** from Bing Webmaster Tools (the
   `AISearchQueriesReport`). Each row is a grounding query Copilot used, with a citation count.
2. **Tokenize the top grounding queries.** Collapse near-duplicates. You will see the
   retriever's vocabulary for your space, e.g. `Citation Rate | Share of Voice | Tools |
   Keyword Ranking ersetzen | Überwachung | ChatGPT Gemini Perplexity | Methoden`.
3. **Cluster the queries.** Different bundles = different intents (e.g. "measure" vs
   "monitor continuously" vs "competitor share of voice"). Each cluster wants its own page.
4. **Map clusters to pages** with the AI Page Stats report. A cluster with high citations
   and no dedicated page is an open opportunity; a cluster with citations split across weak
   pages is a consolidation opportunity.
5. **For each target cluster, build or upgrade one page** that explicitly defines every
   token in the bundle (recipe above). Aim to be the single most complete match.
6. **Re-export monthly.** Watch `Cited Pages` rise as the cluster broadens. Bing grounds
   more pages over time once a topical hub proves citable.

---

## Technical eligibility checklist (Bing-specific)

A "no" here can keep a page out of the index, so nothing else matters.

- [ ] Page is **indexed in Bing** (Bing Webmaster Tools URL Inspection, not just Google).
- [ ] **IndexNow** is wired up so new and updated URLs are pushed to Bing instantly
      (Bing, not Google, consumes IndexNow). This shortens the lag between publishing and
      becoming groundable.
- [ ] Sitemap submitted in **Bing Webmaster Tools**; crawl errors clear.
- [ ] Main content **renders server-side** (Copilot grounding reads the indexed HTML, not
      a client-only React tree).
- [ ] **Bingbot is allowed** in robots.txt. Bing Copilot grounds via the Bing index, so
      blocking Bingbot blocks Copilot citations.
- [ ] `<title>`, meta description, headings and image `alt` are accurate (they feed the
      index and the model's context).
- [ ] No `noindex` / `nosnippet`; canonical is correct; duplicate content controlled.

---

## What Bing rewards that Google explicitly does not

This is where this skill diverges from `google-geo`, and the divergence is evidence-based.
`google-geo` (correctly, per Google's docs) says an "AI-optimized writing style / keyword
phrasing" is **not needed** for Google's AI features. On **Bing**, the opposite held: the
page that most explicitly used the jargon bundle won, by a wide margin. The mechanisms
differ:

| Signal | Google AI features (per google-geo) | Bing / Copilot (per this export) |
|--------|-------------------------------------|----------------------------------|
| Dense, defined domain jargon | "Not needed", systems understand synonyms | **Decisive** — matches grounding-query tokens |
| Named tools + benchmark numbers | Helps as quality, not a special lever | **Strongly correlated** with citation share |
| Grounding-query visibility | Not exposed | **Exposed** in Bing Webmaster Tools (optimize directly) |
| IndexNow | Not consumed by Google | **Consumed** — real ingestion speed-up |
| llms.txt / chunking / schema-for-AI | Not needed | Not the driver here either; term density was |

Do not present this as contradicting Google. Both are true for their own engine. The error
to avoid is optimizing Bing the way you would optimize Google, and assuming term density is
unnecessary. On Bing, the data says it is the whole game.

---

## How to run a Bing GEO audit with this skill

1. **Eligibility first.** Walk the technical checklist. Confirm Bing indexation and
   IndexNow. If a page is not in the Bing index, it cannot be cited; fix that before content.
2. **Pull the AI reports.** Export AI Performance Overview, AI Page Stats, AI Search Queries
   from Bing Webmaster Tools. Without them you are guessing; with them you have the answer key.
3. **Reverse-engineer the grounding queries** (method above). Produce the token bundles and
   clusters.
4. **Score each priority page against the recipe.** For each target cluster, check: are all
   the bundle's tokens present and defined? Named tools? A number per metric? TL;DR, numbered
   framework, query-shaped FAQ, sources? Chunked for extraction?
5. **Prioritize:** consolidate citations onto one best page per cluster; build new pages for
   high-citation clusters that have no owner; do not split one cluster across near-duplicate
   pages (cannibalization).

### Output: `BING-GEO-OPTIMIZATION.md`

1. **Eligibility status** — Bing indexation, IndexNow, Bingbot access, SSR; blockers first.
2. **Citation landscape** — citations per page from the export; concentration and gaps.
3. **Grounding-query clusters** — the token bundles, citation counts, and the page that
   should own each.
4. **Per-page recipe scorecard** — which of the 5 recipe elements each priority page is
   missing.
5. **Top 5 highest-impact actions** — ordered by citations-at-stake vs. effort.

---

## One-line summary

Bing Copilot tells you exactly what it wants: read your grounding queries in Bing Webmaster
Tools, then build one indexed, IndexNow-pushed page per query cluster that defines every
jargon token, names the real tools, and puts a number on every metric. Term density wins.

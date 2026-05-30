---
name: bing-geo-optimization
description: >
  Optimize content to get cited by Microsoft Copilot and Bing's generative AI
  answers. This is the Bing/Copilot specialization of the cross-platform
  marketing-skills:ai-seo skill, narrowed and re-weighted using a real Bing
  Webmaster Tools AI citation export. It keeps ai-seo's framework (the three
  pillars Structure / Authority / Presence and the Princeton GEO methods) and
  adds what only Bing offers: visible grounding queries, the AI Performance / AI
  Page Stats / AI Search Queries reports, the grounding-query
  reverse-engineering method, and IndexNow eligibility. Use when the user says
  "Bing", "Copilot", "Microsoft Copilot", "Bing AI", "grounding queries", "Bing
  Webmaster Tools AI", "IndexNow", or wants citations specifically from Bing /
  Copilot. For Google AI Overviews use google-geo; for the full cross-platform
  playbook use marketing-skills:ai-seo or seo-geo.
---

# Bing & Copilot GEO Optimization

This skill **does not reinvent GEO.** It is the Bing/Copilot specialization of the
closest existing skill, **`marketing-skills:ai-seo`**, which a real citation export
identified as the best predictor of Bing results. Use ai-seo's framework as the base;
use this skill to re-weight it for Bing and to add the Bing-only mechanics.

**Why ai-seo is the base (not google-geo):** an aiseo.hamburg Bing Webmaster Tools AI
export (Feb to late May 2026) was graded against three skills. `marketing-skills:ai-seo`
matched the observed outcome most closely: its Princeton-GEO levers (statistics +37%,
cite sources +40%, technical terms +18%, unique vocabulary +15%, keyword stuffing -10%)
directly predicted which page won. `seo-geo` was a partial match (it over-weights
multimodal, Wikipedia mentions, llms.txt, 134-167 word passages, none of which drove this
result). `google-geo` was the wrong lens for Bing by design (Google says AI-keyword
phrasing is unnecessary; on Bing it was decisive). So this skill inherits ai-seo.

**What the export showed:** one page (`/wissen/ki-sichtbarkeit-messen`) won 248 of 415
citations (~60%); only 10 of 42 pages were cited at all. The winner was the only page that
densely defined the topic jargon, named real tools, and put a number on every metric.

---

## Inherit this from `marketing-skills:ai-seo`

Read ai-seo first. This skill assumes its model and vocabulary:

- **"Cited, not ranked."** The goal is to be a source in the answer, not to rank.
- **The three pillars:** (1) Structure - make it extractable; (2) Authority - make it
  citable; (3) Presence - be where the engine looks.
- **The Princeton GEO method table** (cite sources +40%, statistics +37%, quotations +30%,
  authoritative tone +25%, technical terms +18%, unique vocabulary +15%; keyword stuffing -10%).
- **The extractability checklist** (definition in first lines, self-contained answer
  blocks, stats with sources, comparison tables, query-shaped FAQ, schema, author attribution).
- **The visibility audit** (query the engine, log who is cited, find the gap).
- **Content types that get cited most** (comparison ~33%, definitive guides ~15%, original
  research ~12%).

Everything below is how Bing **re-weights and extends** that base. Do not duplicate ai-seo;
apply it, then layer this.

---

## How Bing/Copilot differs: it shows you the retriever's words

Microsoft Copilot answers via retrieval-augmented generation over the **Bing index**. A
user prompt is rewritten into one or more **grounding queries** (a query fan-out), passages
are retrieved per grounding query, and the model cites what it used. Two consequences set
Bing apart from every other engine ai-seo covers:

1. **Bing exposes the grounding queries to you** (Bing Webmaster Tools -> AI Search
   Queries). No other engine reveals its retriever's own phrasing. This turns ai-seo's
   "guess the query and check" audit into a direct read.
2. **The grounding queries are keyword-dense bundles**, e.g. `Citation Rate Share of Voice
   Tools Keyword Ranking ersetzen`. They reward exactly the levers ai-seo ranks highest
   (technical terms, unique vocabulary, statistics), more sharply than the cross-platform
   average.

---

## Re-weighting the three pillars for Bing

### Pillar 1 - Structure (ai-seo) -> on Bing, term density dominates
ai-seo says make content extractable. Bing adds: **the extractable passage must contain the
grounding query's exact jargon, defined.** In the export, the winner defined Share of Voice
6x with a formula; structurally rich pages with no jargon got zero citations. So, on top of
ai-seo's structure rules:
- Give each key term its own heading + one-sentence definition + a number.
- Name real, branded entities (Ahrefs Brand Radar, Semrush AI Visibility, GA4, GPTBot,
  PerplexityBot), never generic categories. Proper nouns are retrievable anchors.
- Keep ai-seo's 40-60 word answer blocks (this matched Bing better than seo-geo's 134-167).

### Pillar 2 - Authority (ai-seo) -> on Bing, numbers carry the citation
ai-seo's top levers are cite-sources (+40%) and statistics (+37%). Bing confirmed this
bluntly: pages of adjectives were ignored, pages with a benchmark on every metric were
quoted. Put a number, range, or price on every claim ("20-40% Citation Rate", "ab 99
$/Monat"), and keep a named, dated Quellen block.

### Pillar 3 - Presence (ai-seo) -> on Bing, presence means the Bing index + IndexNow
ai-seo says be where the engine looks. For Copilot that is the **Bing index specifically**:
- Confirm indexation in **Bing Webmaster Tools** (not just Google Search Console).
- Wire up **IndexNow** so new/updated URLs reach Bing immediately. Bing consumes IndexNow;
  Google does not. This is a Bing-only presence lever ai-seo does not cover.
- Allow **Bingbot** in robots.txt (Copilot grounds via the Bing index).
- Serve content **server-side** (grounding reads indexed HTML, not a client-only render).

---

## The grounding-query reverse-engineering method (Bing-only)

This replaces ai-seo's "guess and check" audit with the retriever's actual words.

1. **Export the AI Search Queries report** (Bing Webmaster Tools -> AI Performance). Each
   row is a grounding query + citation count. The other two reports: **AI Performance
   Overview** (daily Citations / Cited Pages) and **AI Page Stats** (Citations per URL).
2. **Tokenize the top grounding queries**, collapsing near-duplicates, to get your space's
   retrieval vocabulary.
3. **Cluster by intent** (e.g. "measure" vs "monitor continuously" vs "competitor share of
   voice"). Each cluster wants one owning page.
4. **Map clusters to pages** via AI Page Stats. High-citation cluster with no owner = build.
   One cluster split across weak pages = consolidate (avoid cannibalization).
5. **Build/upgrade one page per cluster** that defines every token in the bundle (the
   re-weighted pillars above). Be the single most complete match.
6. **Re-export monthly.** Watch Cited Pages rise as the hub proves citable.

---

## Technical eligibility checklist (Bing-specific)

A "no" can keep the page out of the index, so it cannot be cited.

- [ ] Indexed in **Bing** (Bing Webmaster Tools URL Inspection).
- [ ] **IndexNow** submitting new/updated URLs (key file at domain root, request to
      `api.indexnow.org/indexnow`).
- [ ] Sitemap submitted in **Bing Webmaster Tools**; crawl errors clear.
- [ ] Main content **server-side rendered**.
- [ ] **Bingbot allowed** in robots.txt.
- [ ] Accurate `<title>`, meta description, headings, image `alt`; correct canonical; no
      `noindex` / `nosnippet`.

---

## Engine-correct conflict with google-geo (do not mis-apply)

| Signal | Google AI features (google-geo) | Bing / Copilot (this export) |
|--------|----------------------------------|------------------------------|
| Dense, defined domain jargon | "Not needed", synonyms understood | **Decisive** - matches grounding-query tokens |
| Grounding-query visibility | Not exposed | **Exposed** in Bing Webmaster Tools |
| IndexNow | Not consumed | **Consumed** |
| Named tools + numbers | Quality, not a special lever | **Strongly correlated** with citation share |

Both positions are correct for their own engine. The error to avoid is optimizing Bing the
way Google's docs prescribe and assuming term density is unnecessary. On Bing the data says
it is the whole game.

---

## How to run a Bing GEO audit with this skill

1. **Apply ai-seo first** for the baseline (pillars, extractability checklist, content type).
2. **Eligibility** - walk the Bing checklist; confirm indexation and IndexNow.
3. **Pull the three AI reports**; reverse-engineer the grounding queries.
4. **Score priority pages** against the re-weighted pillars: every bundle token defined?
   named tools? a number per metric? extraction structure? Bing-indexed and IndexNow-pushed?
5. **Prioritize** - consolidate onto one best page per cluster; build owners for ownerless
   high-citation clusters.

### Output: `BING-GEO-OPTIMIZATION.md`
1. **Eligibility status** (Bing index, IndexNow, Bingbot, SSR) - blockers first.
2. **Citation landscape** (citations per page; concentration and gaps).
3. **Grounding-query clusters** (token bundles, counts, the page that should own each).
4. **Per-page recipe scorecard** (which re-weighted-pillar element each page is missing).
5. **Top 5 highest-impact actions** (citations-at-stake vs effort).

---

## One-line summary

Run `marketing-skills:ai-seo` as the base (it predicted Bing best), then specialize: read
your grounding queries in Bing Webmaster Tools and build one Bing-indexed, IndexNow-pushed
page per cluster that defines every jargon token, names the real tools, and puts a number on
every metric. Term density wins on Bing.

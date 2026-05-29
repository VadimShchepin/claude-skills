---
name: google-geo
description: >
  Optimize content for Google's generative AI features in Search (AI Overviews,
  AI Mode, and AI-organized results) based strictly on Google's official
  Search Central documentation. Covers the AI optimization guide, the
  using-AI-generated-content policy, scaled content abuse, E-E-A-T and the
  Who/How/Why framework, technical eligibility, and Google's own "mythbusting"
  (no llms.txt, no chunking, no special schema needed). Use when the user says
  "Google AI Overviews", "AI Mode", "Google AI optimization", "rank in Google
  AI", "generative AI Search", "AI Overview visibility", or asks what Google
  officially recommends for AI search. For cross-platform GEO (ChatGPT,
  Perplexity, llms.txt, citability scoring), use the seo-geo skill instead.
---

# Google AI Optimization (Search Central, official guidance)

Optimize for Google's generative AI features (AI Overviews, AI Mode, AI-organized
search results) using **only what Google publicly recommends**. This skill is
grounded in Google's Search Central docs, not third-party GEO theory. Where this
contradicts generic GEO advice (llms.txt, content chunking, "AI-specific" writing),
**follow Google.**

**Sources:**
- developers.google.com/search/docs/fundamentals/ai-optimization-guide
- developers.google.com/search/docs/fundamentals/using-gen-ai-content
- developers.google.com/search/docs/essentials/spam-policies (scaled content abuse)
- developers.google.com/search/docs/fundamentals/creating-helpful-content (Who/How/Why, E-E-A-T)

**Choosing between skills:** if the user wants cross-platform AI visibility (ChatGPT,
Perplexity, llms.txt, citability scoring), defer to a cross-platform skill (`seo-geo`,
`ai-seo`). For how this skill relates to the others and when to use which, read
`references/skill-comparison.md`.

---

## Core Premise: SEO still works

Google's AI features (AI Overviews, AI Mode) are built **on top of core Search
ranking and quality systems**. They use retrieval-augmented generation (RAG) and
**query fan-out** (one user query is expanded into many sub-queries). Implications:

- There is **no separate "AI ranking system"** to optimize for. Eligibility for AI
  features flows from the same indexing, ranking, and quality signals as normal Search.
- To be used in a generative AI feature, a page must be **indexed and eligible to be
  shown in Google Search with a snippet**.
- Strong foundational SEO = strong AI feature visibility. There is no shortcut around it.

---

## The 4 things Google tells you to do

### 1. Create valuable, non-commodity content
- Provide a **unique point of view**: original analysis, first-hand experience, or
  reporting, rather than restating what already exists.
- Make it **helpful, reliable, and people-first**, with expert insight beyond common knowledge.
- Organize with clear paragraphs, sections, and headings for readability.
- Include high-quality images and video where they genuinely help.
- Guiding principle: *"focus on what your visitors would enjoy, find helpful, and feel
  satisfied with after visiting your website."* Don't overdo it (that crosses into manipulation).

### 2. Build clear technical structure
- The page must be **indexed and snippet-eligible**.
- Content must be **publicly accessible and crawlable** (Google's AI features use
  publicly accessible, crawlable content).
- Follow **JavaScript SEO** best practices if using a JS framework (content must render
  for Googlebot, not only in the browser).
- Provide good **page experience** across devices, reduce latency.
- Reduce duplicate content.

### 3. Optimize local and ecommerce details
- Use **Google Merchant Center** feeds and **Google Business Profile** so product,
  service, and local info is structured and current.
- Consider conversational/agentic surfaces (e.g. Business Agent) for engagement.

### 4. If you use AI tools to create content, meet the bar
- Output must meet **Search Essentials** and **spam policies**, especially **scaled
  content abuse** (see below).

---

## Mythbusting: what Google says you do NOT need

This is the most valuable, most counter-intuitive part. Google explicitly states these
are **not required** for generative AI visibility. Do not waste effort here for Google's
sake (you may still do some for other platforms via the `seo-geo` skill):

| Common claim | Google's position |
|--------------|-------------------|
| Create `llms.txt` / special AI text files / Markdown | **Not needed.** "You don't need to create new machine readable files, AI text files, markup, or Markdown." |
| "Chunk" content into AI-friendly blocks | **Not needed.** Google systems understand nuance and structure. |
| Use an "AI-optimized" writing style / keyword phrasing | **Not needed.** Systems understand synonyms and meaning. |
| Add structured data so AI can read the page | **Not required** for AI feature eligibility (structured data still helps for rich results — different goal). |
| Chase inauthentic brand mentions across the web | **Ineffective.** |

**Practical rule:** if a tactic exists only to "feed the AI" and adds nothing for a human
reader, Google says skip it. Spend that time on genuinely better content and clean technical SEO.

---

## Technical eligibility checklist

Confirm each. A "no" disqualifies the page from AI features regardless of content quality.

- [ ] Page is **indexed** (`site:` check / URL Inspection in Search Console).
- [ ] Page is **snippet-eligible** (no `nosnippet`, no `noindex`, no blocking `data-nosnippet`).
- [ ] Page is **crawlable** (not blocked in `robots.txt`; Googlebot can reach it).
- [ ] Main content **renders without client-side JS** (or JS is server-rendered / hydrated for Googlebot).
- [ ] Good **page experience**: mobile-friendly, low latency, stable layout.
- [ ] **No duplicate-content** dilution; canonical is correct.
- [ ] `<title>`, meta description, headings, and image `alt` are accurate and useful
      (these surface in results and give the model context).

---

## Using AI-generated content (Google's policy)

Google does **not** prohibit AI-generated content. It judges **quality, not method of
production**. But there are hard lines and explicit expectations.

### The hard line: scaled content abuse
> "Scaled content abuse is when many pages are generated for the primary purpose of
> manipulating search rankings and not helping users."

Examples that violate it:
- Generating numerous pages with AI tools that add no user value.
- Scraping feeds or search results with minimal added value.
- Stitching content from multiple sources without enhancement.
- Spinning up multiple sites to hide the scaled nature of the content.
- Producing many keyword-stuffed pages with little coherent meaning.

Intent and scale are what matter, **not** whether AI was used. One genuinely helpful
AI-assisted page is fine; ten thousand thin ones are abuse.

### Quality expectations
> "Focus on accuracy, quality, and relevance, particularly when content is generated
> automatically."

This explicitly includes the metadata that AI-generated pipelines often neglect:
`<title>` elements, meta descriptions, structured data, and image `alt` text.

### Transparency (give users context)
- Sharing **how a piece of content was created** helps readers and is encouraged.
- For automated content, consider disclosing the use of automation and giving background
  on how it was produced.

### Ecommerce / Merchant Center specifics
- AI-generated **images** must carry IPTC `DigitalSourceType` metadata labeled
  `TrainedAlgorithmicMedia`.
- AI-generated **product attributes** must be specified separately and **labeled as AI-generated**.

### Structured data, if used
- Follow general structured data guidelines + the specific guidelines for each feature.
- **Validate** the markup so it's eligible (use the Rich Results Test).

---

## E-E-A-T and the Who / How / Why framework

Google assesses content for **Experience, Expertise, Authoritativeness, Trustworthiness**.
**Trust is the most important**; the others feed into it. Run content through these.

### Who created it
- [ ] Is it **self-evident who authored** the content?
- [ ] Do pages carry **bylines** where readers would expect them?
- [ ] Do bylines link to **author background / credentials**?

### How it was made
- [ ] Is any **automation / AI generation self-evident** to the visitor where relevant?
- [ ] If automated, do you **explain why automation was useful** to the reader?

### Why it exists
- [ ] Is the content made **primarily to help people**, not to manipulate rankings?
      ("People-first content is created primarily for people, not to manipulate search engine rankings.")

---

## Content self-assessment (Google's own questions)

Use these to audit a page. Honest "no" answers mark the work to do.

**Content & quality**
- Does it provide **original** information, reporting, research, or analysis?
- Is the description **substantial, complete, or comprehensive**?
- Does it offer **insightful analysis beyond the obvious**?
- Does the main heading **avoid exaggeration / clickbait**?
- Is this a page you'd **bookmark or share**?
- Is it free of spelling/stylistic problems and not mass-produced across a large network?

**Expertise**
- Does it present information in a way that makes you **trust it** (clear sourcing, evidence)?
- Would experts/enthusiasts recognize it as a **well-trusted authority**?
- Is it written by someone **demonstrably knowledgeable** about the topic?
- Is it free of **easily verified factual errors**?

---

## Emerging: agentic experiences

Google flags AI **agents** that may interact with sites via browser automation, DOM
inspection, and the accessibility tree. To stay usable by them:
- Keep markup **semantic and accessible** (proper roles, labels, headings).
- Ensure critical actions/content are reachable without bespoke JS interactions.
- Watch the **Universal Commerce Protocol (UCP)** and related standards for transactions.

This is forward-looking, not a current ranking factor. Good accessibility = good agent-readiness.

---

## How to run an audit with this skill

1. **Eligibility first.** Walk the technical eligibility checklist. If a page can't be
   indexed/crawled/snippet-shown, nothing else matters yet.
2. **Quality & originality.** Run the content self-assessment + Who/How/Why. Flag thin,
   derivative, or unattributed sections.
3. **AI-content policy.** If AI was used to produce pages at scale, test against the
   scaled content abuse definition. Check metadata quality and Merchant Center labeling.
4. **Mythbusting pass.** Identify effort being spent on Google-irrelevant tactics
   (llms.txt for Google, chunking, AI-keyword phrasing) and redirect it.
5. **Local/ecommerce.** Confirm Business Profile + Merchant Center are populated and current.

### Output: `GOOGLE-AI-OPTIMIZATION.md`

1. **Eligibility status** — pass/fail per checklist item, with the blocking issues first.
2. **Quality & E-E-A-T findings** — failed self-assessment questions, missing bylines/sourcing.
3. **AI-content policy risk** — scaled content abuse exposure, metadata gaps, image/attribute labeling.
4. **Wasted effort to stop** — Google-irrelevant tactics found on the site.
5. **Local & ecommerce** — Business Profile / Merchant Center gaps.
6. **Top 5 highest-impact actions**, ordered by effort vs. eligibility impact.

---

## One-line summary

For Google's AI features, there is no separate game: be indexed and crawlable, write
genuinely original people-first content with clear authorship, don't mass-produce thin
pages, and ignore the AI-specific tactics (llms.txt, chunking, special markup) that Google
says you don't need.

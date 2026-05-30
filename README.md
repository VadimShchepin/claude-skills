# claude-skills

A personal [Claude Code](https://claude.com/claude-code) skills **marketplace**. Each skill
is its own plugin, so you install only the ones you want.

## Add the marketplace

```
/plugin marketplace add VadimShchepin/claude-skills
```

Then install individual skills:

```
/plugin install google-geo@claude-skills
/plugin install bing-geo-optimization@claude-skills
```

## Skills

| Skill | What it does |
|-------|--------------|
| [`google-geo`](plugins/google-geo) | Optimize for Google's generative AI features (AI Overviews, AI Mode) using Google's **own** Search Central guidance, including the mythbusting that llms.txt, content chunking, and special schema are not needed for Google. |
| [`bing-geo-optimization`](plugins/bing-geo-optimization) | The **Bing/Copilot specialization of `marketing-skills:ai-seo`**, re-weighted using a **real Bing Webmaster Tools AI citation export**. Inherits ai-seo's three pillars + Princeton GEO methods, then adds the Bing-only mechanics: visible grounding queries, the AI reports, the reverse-engineering method, and IndexNow. |

---

## What `google-geo` covers

- **Core premise:** Google's AI features run on the existing ranking and quality systems via
  RAG and query fan-out. No separate "AI ranking" exists. Eligibility = indexed + snippet-eligible.
- **The 4 official recommendations:** non-commodity people-first content; clean technical
  structure; local/ecommerce data (Business Profile + Merchant Center); meet the quality bar
  when using AI tools.
- **Mythbusting:** what Google explicitly says you do **not** need (llms.txt, chunking,
  AI-writing style, schema-for-AI, bought brand mentions).
- **Technical eligibility checklist**, the **scaled content abuse** policy, **E-E-A-T +
  Who/How/Why**, and an audit workflow that outputs `GOOGLE-AI-OPTIMIZATION.md`.

It ships with a [deep comparison](plugins/google-geo/skills/google-geo/references/skill-comparison.md)
against other AI-SEO skills (`seo-geo`, `seo-content`, `marketing-skills:ai-seo`), explaining
when to use which. Short version: those recommend llms.txt, chunking, and schema-for-AI;
Google says those do nothing for **its** AI features (they still help ChatGPT/Perplexity), so
`google-geo` is the conservative, source-backed reference for Google specifically.

Sources: Google Search Central
[AI optimization guide](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide),
[Using AI-generated content](https://developers.google.com/search/docs/fundamentals/using-gen-ai-content),
[Spam policies](https://developers.google.com/search/docs/essentials/spam-policies),
[Creating helpful content](https://developers.google.com/search/docs/fundamentals/creating-helpful-content).

---

## What `bing-geo-optimization` covers

This skill is a **specialization of `marketing-skills:ai-seo`**, the skill a real Bing
Webmaster Tools AI citation export picked as the closest predictor of Bing results. It does
not reinvent GEO: run ai-seo as the base (its three pillars and Princeton GEO methods), then
this skill re-weights them for Bing and adds the Bing-only mechanics below.

- **Core premise:** Microsoft Copilot grounds on the Bing index via query fan-out. A user
  prompt becomes keyword-dense **grounding queries**, and Bing Webmaster Tools shows them to
  you. No other engine exposes its retriever's own words.
- **The validated recipe:** the page that won ~58% of citations was the only one combining
  defined jargon (as glossable units) + named branded tools + a benchmark number on every
  metric + extraction-friendly structure + "displaced the old thing" framing. Structurally
  rich but jargon-light pages got **zero** citations. Term density is the moat.
- **The grounding-query reverse-engineering method:** export the AI Search Queries report,
  tokenize and cluster the grounding queries, map clusters to pages, and build one complete
  page per cluster.
- **Bing-specific eligibility:** Bing indexation, **IndexNow** (Bing consumes it, Google does
  not), Bingbot access, SSR. Outputs `BING-GEO-OPTIMIZATION.md`.

It ships with a [comparison](plugins/bing-geo-optimization/skills/bing-geo-optimization/references/skill-comparison.md)
explaining the engine-correct conflict with `google-geo`: Google officially says AI-keyword
phrasing is unnecessary; on Bing the dense jargon bundle was decisive. Both are true, for
different engines.

---

## Adding a new skill to this marketplace

1. Create `plugins/<skill-name>/.claude-plugin/plugin.json` and
   `plugins/<skill-name>/skills/<skill-name>/SKILL.md`.
2. Add one entry to the `plugins` array in `.claude-plugin/marketplace.json` with
   `"source": "./plugins/<skill-name>"`.
3. Commit and push. Users re-run `/plugin marketplace update claude-skills` to see it.

## License

MIT. See [LICENSE](LICENSE).

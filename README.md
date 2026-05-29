# google-geo

A Claude Code skill for optimizing toward **Google's generative AI features** (AI Overviews,
AI Mode, AI-organized results), grounded strictly in **Google's own Search Central
documentation** rather than third-party GEO theory.

Where this skill contradicts popular GEO advice (llms.txt, content chunking, "AI-specific"
writing, schema-for-AI), it follows Google. That is the point: Google says those tactics do
not help its AI features, and this skill carries that position verbatim.

> Companion: for **cross-platform** GEO (ChatGPT, Perplexity, Copilot, llms.txt, passage
> citability), use a cross-platform skill such as `seo-geo` or `ai-seo`. See the
> [skill comparison](skills/google-geo/references/skill-comparison.md) for when to use which.

---

## What it covers

- **Core premise:** Google's AI features run on the existing ranking and quality systems via
  RAG and query fan-out. No separate "AI ranking" exists. Eligibility = indexed + snippet-eligible.
- **The 4 official recommendations:** non-commodity people-first content; clean technical
  structure; local/ecommerce data (Business Profile + Merchant Center); meet the quality bar
  when using AI tools.
- **Mythbusting:** what Google explicitly says you do **not** need (llms.txt, chunking,
  AI-writing style, schema-for-AI, bought brand mentions).
- **Technical eligibility checklist:** indexable, crawlable, snippet-eligible, server-rendered.
- **AI-generated content policy:** the `scaled content abuse` definition + examples,
  transparency expectations, Merchant Center image/attribute labeling.
- **E-E-A-T + Who/How/Why** framework and Google's own content self-assessment questions.
- **Audit workflow** that outputs a `GOOGLE-AI-OPTIMIZATION.md` report.

---

## Install

### As a plugin (recommended)

```
/plugin marketplace add VadimShchepin/google-geo
/plugin install google-geo
```

(Update the GitHub path above to wherever you host this repo.)

### Manual

Copy the skill into your skills directory:

```bash
cp -r skills/google-geo ~/.claude/skills/google-geo   # global
# or: cp -r skills/google-geo .claude/skills/google-geo  # per-project
```

---

## When it triggers

"Google AI Overviews", "AI Mode", "Google AI optimization", "rank in Google AI",
"generative AI Search", "AI Overview visibility", or "what does Google officially recommend
for AI search".

---

## How it compares to other AI-SEO skills

Five skills overlap this use case. The short version:

| Skill | Scope | Identity |
|-------|-------|----------|
| **google-geo** | Google only | Google's official guidance + mythbusting |
| seo-geo | Cross-platform | Citability scoring, llms.txt, brand mentions |
| seo | Umbrella | Routes `/seo geo` to seo-geo |
| seo-content | Content slice | E-E-A-T + citation readiness |
| ai-seo (marketing-skills) | Cross-platform, GTM-led | "Cited not ranked", query-based audits |

The key tension: seo-geo, seo-content, and ai-seo all recommend llms.txt, passage chunking,
and schema-for-AI. Google says those do nothing for **its** AI features (they still help
ChatGPT/Perplexity). google-geo is the conservative reference you use to fact-check the others
when the question is narrowly about Google.

Full analysis: [skills/google-geo/references/skill-comparison.md](skills/google-geo/references/skill-comparison.md).

---

## Sources

- [Google Search Central: AI optimization guide](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)
- [Google Search Central: Using AI-generated content](https://developers.google.com/search/docs/fundamentals/using-gen-ai-content)
- [Google Search Central: Spam policies (scaled content abuse)](https://developers.google.com/search/docs/essentials/spam-policies)
- [Google Search Central: Creating helpful content (E-E-A-T, Who/How/Why)](https://developers.google.com/search/docs/fundamentals/creating-helpful-content)

## License

MIT. See [LICENSE](LICENSE).

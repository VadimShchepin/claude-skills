# Where bing-geo-optimization sits in the GEO skill landscape

Several skills claim the "optimize for AI search" job and their advice partly contradicts.
The contradiction is a **scope difference by engine**, not a bug. This skill is the
**Bing / Copilot** specialist, and uniquely it is grounded in a real citation export rather
than in studies or vendor docs.

Last reviewed: May 2026.

---

## The skills that touch this use case

| Skill | Engine scope | Core grounding | One-line identity |
|-------|--------------|----------------|-------------------|
| **bing-geo-optimization** (this) | Bing + Microsoft Copilot only | A real Bing Webmaster Tools AI citation export | "What Bing's grounding queries actually cited, and how to reproduce it" |
| **google-geo** | Google only (AI Overviews, AI Mode) | Google Search Central docs | "What Google officially says, including what it says you don't need" |
| **seo-geo** | Cross-platform (AIO, ChatGPT, Perplexity, Copilot) | Industry studies (Ahrefs, Princeton, SparkToro) | "Citability scoring + brand-mention strategy across all engines" |
| **ai-seo** (marketing-skills) | Cross-platform, business-led | GTM / Princeton GEO framing | "Get cited not ranked; audit by querying the engines" |

---

## This skill is a specialization of `ai-seo`, not a sibling

The other rows are alternative skills. `bing-geo-optimization` is different: it **extends
`marketing-skills:ai-seo`**, the skill a real citation export identified as the closest
predictor of Bing results. It inherits ai-seo's three pillars (Structure / Authority /
Presence) and Princeton GEO method table, then re-weights them for Bing and adds the
Bing-only mechanics (visible grounding queries, the AI Performance reports, IndexNow). Run
ai-seo as the base, then layer this. It is not built on `google-geo`; google-geo is the
wrong lens for Bing by design (see the conflict below).

## What makes this skill distinct

- **It is the only one with ground truth.** google-geo cites Google's docs; seo-geo and
  ai-seo cite published studies. This skill is built from an actual per-URL, per-grounding-query
  citation export, so its core claim (term density wins on Bing) is observed, not inferred.
  That same export is why it inherits ai-seo specifically: ai-seo's levers matched the data,
  seo-geo's only partially, google-geo's not at all (for Bing).
- **It optimizes against the retriever's own words.** Bing Webmaster Tools exposes grounding
  queries. No other engine does. The workflow here (reverse-engineer the grounding queries)
  has no equivalent in the Google or cross-platform skills.
- **It is engine-correct about a real conflict.** google-geo says AI-keyword phrasing is
  unnecessary; on Bing the dense, defined jargon bundle was decisive. Both are true for their
  own engine. Mis-applying one to the other is the error to avoid.

---

## The core conflict, stated plainly

`google-geo` (per Google's docs) says, for **Google's** AI features: you do not need an
AI-specific writing style, keyword phrasing, llms.txt, content chunking, or schema-for-AI.

This skill found, for **Bing / Copilot**: the page that most explicitly used the topic's
jargon bundle (defined terms + named tools + numbers) won ~58% of citations, while
structurally rich but jargon-light pages got zero.

**Both are correct, for different engines.** Bing's grounding fan-out rewrites queries into
keyword-dense strings and retrieves the closest lexical+semantic match; term density helps
there. Google's pipeline reads your normally-indexed pages and is told (officially) not to
expect AI-phrasing tricks. Do not optimize Bing like Google or vice versa.

---

## Decision matrix

| Situation | Use |
|-----------|-----|
| Goal is **Bing / Microsoft Copilot** citations; you have Bing Webmaster Tools AI data | **bing-geo-optimization** |
| You can see your **grounding queries** and want to optimize against them | **bing-geo-optimization** |
| Goal is **Google AI Overviews / AI Mode** specifically | **google-geo** |
| Cross-platform (ChatGPT + Perplexity + Google + Bing) push | **seo-geo** (sanity-check Google claims against google-geo, Bing claims against this) |
| Founder/marketer: pick queries, scope competitors, audit by querying engines | **ai-seo** |

---

## Recommended pairing

For a client targeting all major AI engines:

1. **google-geo** for the Google-eligibility and quality baseline (also lifts every engine
   because it improves the underlying content).
2. **bing-geo-optimization** for Bing/Copilot, optimizing directly against the exported
   grounding queries with the term-density recipe.
3. **seo-geo / ai-seo** for ChatGPT and Perplexity (llms.txt, brand mentions, passage
   formatting) and for the commercial framing.

The one rule: attribute each tactic to the engine the evidence supports. Term-density-for-Bing
and "no-AI-phrasing-needed-for-Google" are not in conflict; they are two engines.

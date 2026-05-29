# GEO / AI-SEO skill landscape: a deep comparison

This reference exists because **several skills claim the "optimize for AI search" job**, and
their advice partly contradicts each other. The contradiction is not a bug. It is a scope
difference. This document maps the landscape so you pick the right tool and never apply
ChatGPT/Perplexity tactics to Google (or vice versa) by accident.

Last reviewed: May 2026.

---

## The five skills that touch this use case

| Skill | Owner / source | Engine scope | Core grounding | One-line identity |
|-------|----------------|--------------|----------------|-------------------|
| **google-geo** (this) | Google Search Central docs | Google only (AI Overviews, AI Mode) | Google's official guidance | "What Google actually says, including what it says you don't need" |
| **seo-geo** | local global skill | Cross-platform | Industry studies (Ahrefs, Princeton, SparkToro) | "Citability scoring + brand-mention strategy across all AI engines" |
| **seo** | local global skill | Umbrella | Orchestrator over 12 sub-skills | "Full SEO suite; `/seo geo` delegates to seo-geo" |
| **seo-content** | local global skill | Content slice | QRG E-E-A-T + content quality | "Is this page good and citable?" |
| **ai-seo** (marketing-skills) | Corey Haines plugin | Cross-platform, business-led | GTM / conversion framing | "Get cited, not just ranked; audit by querying the engines" |

---

## What each one is actually for

### google-geo (this skill)
- **Engine:** Google's generative features only.
- **Posture:** deliberately conservative. It refuses tactics Google calls unnecessary.
- **Best for:** a client or page where the goal is Google AI Overviews / AI Mode, and you
  want defensible, source-backed recommendations (no speculation).
- **Unique value:** the only skill here that carries Google's explicit "you do NOT need
  llms.txt / chunking / AI-writing / schema-for-AI" position, plus the scaled-content-abuse
  definition and the Who/How/Why framework verbatim from Google.

### seo-geo
- **Engine:** Google AIO + ChatGPT + Perplexity + Copilot.
- **Posture:** maximalist. Implements the full GEO playbook.
- **Best for:** a cross-platform AI-visibility push where ChatGPT and Perplexity matter as
  much as Google.
- **Signature mechanics:** 134-167 word citable passages, llms.txt, RSL licensing,
  brand-mention correlation data, platform-specific citation-source tables.

### seo (umbrella)
- **Engine:** everything, via routing.
- **Best for:** "do a full SEO audit." It calls seo-geo for the GEO portion. Use it as the
  entry point, not as a GEO authority in itself.

### seo-content
- **Engine:** content quality + E-E-A-T, with an "AI citation readiness" sub-score.
- **Best for:** judging whether a single page is substantive, trustworthy, and extractable.
- **Overlap note:** its "AI citation readiness" advice (structured answers, schema, FAQ)
  leans cross-platform, same caveat as seo-geo below.

### ai-seo (marketing-skills)
- **Engine:** cross-platform, framed for founders/marketers.
- **Best for:** the go-to-market angle: which queries to win, who competitors are, how to
  audit by actually asking ChatGPT/Perplexity what they return.
- **Signature mechanics:** conversational visibility audit, extractability checklist,
  "cited not ranked" framing, platform ranking-factor references.

---

## The core conflict, stated plainly

`seo-geo`, `seo-content`, and `ai-seo` all recommend, as GEO tactics:

1. Create an **llms.txt**.
2. Write **134-167 word self-contained passages** (content chunking).
3. Add **schema markup so AI can parse the page**.
4. Adopt an **answer-first, AI-extractable writing style**.

Google's own documentation states, for **Google's** AI features specifically, that all four
are **not required**:

> "You don't need to create new machine readable files, AI text files, markup, or Markdown"
> (llms.txt named as an example). Content chunking "has no requirement." There is no need for
> an AI-specific writing style. Structured data "is not required" for generative AI visibility.

**Both sides are correct, for different engines.** llms.txt and passage chunking demonstrably
help RAG systems like ChatGPT and Perplexity; they do nothing for Google's pipeline, which
reads your normally-indexed, normally-ranked pages. The danger is only mis-attribution:
selling llms.txt as a *Google AI Overviews* lever is wrong.

---

## Decision matrix: which skill to reach for

| Situation | Use |
|-----------|-----|
| Goal is **Google AI Overviews / AI Mode** specifically | **google-geo** |
| Client asks "what does Google officially say / will this get us penalised" | **google-geo** |
| Cross-platform AI visibility (ChatGPT + Perplexity + Google) | **seo-geo** (then sanity-check Google claims against google-geo) |
| "Audit my whole site's SEO" | **seo** (umbrella) |
| "Is this article good enough / trustworthy enough" | **seo-content** |
| Founder/marketer: pick queries, scope competitors, audit by querying engines | **ai-seo** |
| Adding structured data for rich results (not AI) | **seo-schema** / **schema-markup** |

Rule of thumb: **google-geo is the conservative, source-backed reference. seo-geo / ai-seo
are the expansive, cross-platform playbooks.** Use google-geo to fact-check the others when
the question is narrowly about Google.

---

## Recommended pairing

For a real client engagement targeting all major AI engines:

1. Run **google-geo** for the Google-eligibility and quality baseline (this is non-negotiable
   and the same work also lifts ChatGPT/Perplexity because it improves the underlying content).
2. Layer **seo-geo** for cross-platform extras (llms.txt, passage formatting, brand mentions),
   clearly labelled as "for ChatGPT / Perplexity, not for Google."
3. Use **ai-seo** to frame the engagement commercially and to run the query-based visibility
   audit that none of the others do.

The one thing to never do: present llms.txt, chunking, or schema-for-AI as a Google AI
Overviews ranking factor. That is the single most common error this landscape produces.

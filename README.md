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
```

## Skills

| Skill | What it does |
|-------|--------------|
| [`google-geo`](plugins/google-geo) | Optimize for Google's generative AI features (AI Overviews, AI Mode) using Google's **own** Search Central guidance, including the mythbusting that llms.txt, content chunking, and special schema are not needed for Google. |

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

## Adding a new skill to this marketplace

1. Create `plugins/<skill-name>/.claude-plugin/plugin.json` and
   `plugins/<skill-name>/skills/<skill-name>/SKILL.md`.
2. Add one entry to the `plugins` array in `.claude-plugin/marketplace.json` with
   `"source": "./plugins/<skill-name>"`.
3. Commit and push. Users re-run `/plugin marketplace update claude-skills` to see it.

## License

MIT. See [LICENSE](LICENSE).

# SEO · GEO · AdSense Content Skills

A Claude Code plugin: write quality web content and get a site ready for AdSense review.
9 skills plus 4 agents, orchestrated end to end. See [AGENT-FLOWS.md](AGENT-FLOWS.md) for
flowcharts of how each agent works.

**This is not a guarantee of AdSense approval.** Nothing here can promise that; it improves the
things Google's review actually looks at.

## Install

### Option A — as a plugin (recommended)

```
/plugin marketplace add Maulik-008/seo-geo-adsense-skills
/plugin install seo-geo-adsense-skills@seo-geo-adsense-skills
```

Or from a terminal, without opening Claude Code interactively:

```bash
claude plugin marketplace add Maulik-008/seo-geo-adsense-skills
claude plugin install seo-geo-adsense-skills@seo-geo-adsense-skills
```

Check it installed and see what it added:

```bash
claude plugin list
claude plugin details seo-geo-adsense-skills
```

Remove it the same way:

```bash
claude plugin uninstall seo-geo-adsense-skills@seo-geo-adsense-skills
claude plugin marketplace remove seo-geo-adsense-skills
```

### Option B — copy the folders manually

If you don't want the plugin manager tracking updates, copy the skills and agents directly:

```bash
git clone https://github.com/Maulik-008/seo-geo-adsense-skills.git
cp -r seo-geo-adsense-skills/skills/* ~/.claude/skills/
cp seo-geo-adsense-skills/agents/*.md ~/.claude/agents/
```

On Windows, the targets are `%USERPROFILE%\.claude\skills\` and `%USERPROFILE%\.claude\agents\`.
Restart Claude Code afterward.

## What's in it

| Kind | Name | Purpose |
|---|---|---|
| Skill | `adsense-content-pipeline` | Orchestrates the full readiness workflow; the rulebook the agents follow |
| Skill | `adsense-auditor` | 73-item AdSense eligibility and policy audit |
| Skill | `human-web-content` | Default writer for web pages |
| Skill | `clarity` | Writer for authored essays and personal prose |
| Skill | `content-quality-auditor` | 80-item CORE-EEAT content-quality score |
| Skill | `geo-content-optimizer` | Makes content citable by AI search engines |
| Skill | `serp-markup-builder` | Titles, meta, OG/Twitter tags, JSON-LD |
| Skill | `seo-geo` | SEO/GEO research, keyword and SERP tools |
| Skill | `pagewell` | Pages-as-code, topic clusters, discovery files (repo sites only) |
| Agent | `adsense-readiness-checker` | Read-only full-site AdSense inspection and decision |
| Agent | `content-quality-rewriter` | Audits and rewrites existing content |
| Agent | `serp-snippet-writer` | Human-sounding titles, meta, and schema |
| Agent | `adsense-content-loop` | Research → write → audit → markup loop for new pages |

Full flowcharts for each agent: [AGENT-FLOWS.md](AGENT-FLOWS.md).

## How to trigger each one

There are two different mechanisms here, and they're invoked differently:

- **Skills** get a slash command: type `/<skill-name>` and it runs. You can also just describe
  the task in plain language and Claude will pick the matching skill on its own.
- **Agents have no slash command.** Claude Code doesn't put agents in the `/` menu. You trigger
  an agent by describing the task in plain language — Claude reads your request against every
  installed agent's description and delegates to the one that matches — or by naming it
  explicitly: *"Use the `adsense-content-loop` agent to ..."*. Both work; naming it directly is
  more reliable when several agents or skills could plausibly match.

Either way, **more specific input gets a better result.** Vague requests ("write me a blog post")
force the agent to guess at your site, audience, and topic. Use the templates below — fill in the
bracketed parts and delete what you don't have.

### Agents

#### `adsense-content-loop` — research, write, and check new pages

```
Use adsense-content-loop:
Topics: [topic 1], [topic 2], [topic 3]
Site: [URL or one-line description of the niche]
Audience: [who reads this, and market/language, e.g. "Indian freelancers, English"]
Author expertise / first-hand material: [what you or your writer actually know or have done — or "none"]
Output folder: [optional, default ./content/]
```

Example:

> Use adsense-content-loop: 3 articles — "GSTR-1 for freelancers", "UPI transaction limits by bank", "Section 44ADA explained". Site example.in, Indian freelancers. Author: CA, 6 years' practice. Output: ./content/.

Returns a folder per topic (`research.md`, `article.md`, `head.html`, `audit.md`) plus a
`REPORT.md`. It will not publish anything, and it stops and asks a question if the site, topic,
or audience is missing.

#### `adsense-readiness-checker` — is my site ready for AdSense?

```
Use adsense-readiness-checker on [site URL].
Stage: [pre-application | rejected | limited]
Rejection message (if any): "[paste the exact text from the AdSense Sites page]"
Account facts (if relevant): [existing AdSense account? traffic sources?]
```

Example:

> Use adsense-readiness-checker on https://example.in. Stage: rejected, message "Low value content". Traffic is organic plus Instagram. No existing AdSense account.

Read-only — it never edits your site. Returns `ADSENSE-READINESS-REPORT.md` with a decision
(Not ready / Ready after fixes / Ready), every one of the 73 AdSense checklist items, and an
ordered fix list naming which agent or skill handles each fix.

#### `content-quality-rewriter` — audit and fix content you've already written

```
Use content-quality-rewriter on [file paths, URLs, or pasted text].
Site/niche: [what the site is about]
Audience: [who reads it]
Mode: [improve (light edit) | rewrite (full rewrite) — optional, it will decide if you skip this]
Author's real experience/material: [optional, use where it fits]
```

Example:

> Use content-quality-rewriter on content/posts/gst-for-freelancers.md and content/posts/upi-limits.md. Site: Indian personal-finance blog, audience Indian freelancers. I'm a CA with 6 years of practice; use that where it fits.

Writes `<file>.rewritten.md` next to each original — it never overwrites the original — plus a
report with before/after scores and a list of questions only you can answer.

#### `serp-snippet-writer` — human-sounding titles, meta tags, and schema

```
Use serp-snippet-writer on [page URLs, files, or pasted content].
Brand: [site/brand name]
Keyword (optional): [target keyword per page]
Market: [optional, e.g. "India, English"]
Mode: [report (default, writes options for you to choose) | apply (edits the head tags directly)]
```

Example:

> Use serp-snippet-writer on https://example.in/blog/ (all posts in the sitemap). Brand: Example Finance. Market: India, English. Report mode.

Returns 3 title + 3 description options per page with one recommended, plus OG/Twitter tags,
alt text, and validated JSON-LD. Titles are checked against a "would a real person say this out
loud?" test — see `skills/serp-markup-builder/references/human-title-rules.md`.

### Skills

Trigger these with `/<name>`, or just describe the task — each skill's own description below is
what Claude matches your request against.

| Skill | Slash command | Use it when you say things like | Minimal example |
|---|---|---|---|
| `adsense-content-pipeline` | `/adsense-content-pipeline` | "get my site AdSense approved", "prepare my blog for AdSense", "fix my AdSense rejection" | `/adsense-content-pipeline site: example.in, stage: pre-application` |
| `adsense-auditor` | `/adsense-auditor` | "can my site pass AdSense review?", "why would AdSense reject this?", "check my ads.txt / privacy policy" | `/adsense-auditor https://example.in` |
| `human-web-content` | `/human-web-content` | "write a blog post about X", "this article sounds like ChatGPT wrote it", "make this less AI-sounding" | `/human-web-content Write a 900-word guide on UPI transaction limits, for Indian freelancers` |
| `clarity` | `/clarity` | "rewrite this essay", "review my newsletter draft", "help me write this in my own voice" | `/clarity rewrite: [paste draft]` |
| `content-quality-auditor` | `/content-quality-auditor` | "score this page's E-E-A-T", "is this publish-ready?", "run a CORE-EEAT audit" | `/content-quality-auditor Audit this how-to-guide for the US market: [URL or paste]` |
| `geo-content-optimizer` | `/geo-content-optimizer` | "optimize this for AI citations", "make ChatGPT/Perplexity cite this page" | `/geo-content-optimizer Optimize this paragraph for AI citation: [paste]` |
| `serp-markup-builder` | `/serp-markup-builder` | "write title tags and meta descriptions", "generate FAQ/Product schema", "add Open Graph tags" | `/serp-markup-builder meta: Create meta tags for a blog post about "how to start a podcast"` |
| `seo-geo` | `/seo-geo` | "do keyword research", "audit this site's SEO", "why isn't this page ranking" | `/seo-geo Audit https://example.in for basic SEO issues` |
| `pagewell` | `/pagewell` | "plan a topic cluster", "generate a FAQ/glossary page as code", "build a free tool page" | `/pagewell Plan a topic cluster for "GST for freelancers"` |

### Which one should I actually use?

```
New pages, from scratch, researched and checked  → adsense-content-loop (agent)
Already-written content that needs fixing         → content-quality-rewriter (agent)
Just the titles/meta/schema, content is fine      → serp-snippet-writer (agent)
"Is my whole site ready to apply?"                → adsense-readiness-checker (agent)
Full end-to-end plan across a whole site           → /adsense-content-pipeline (skill)
One specific check or one specific writing task    → the matching skill above
```

## Licensing

Several skills are original work for this project; a few are adapted from third-party sources
under their own licenses. See [LICENSE-NOTICES.md](LICENSE-NOTICES.md) before reusing or
redistributing individual skills.

## Publishing your own fork

If you fork or rename this repository, update the `source`, `homepage`, and `repository` fields
in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) and
[`.claude-plugin/plugin.json`](.claude-plugin/plugin.json) to point at your fork, and run
`claude plugin validate .` before publishing.

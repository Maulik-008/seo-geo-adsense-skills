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

Full flowcharts and example prompts for each agent: [AGENT-FLOWS.md](AGENT-FLOWS.md).

## Licensing

Several skills are original work for this project; a few are adapted from third-party sources
under their own licenses. See [LICENSE-NOTICES.md](LICENSE-NOTICES.md) before reusing or
redistributing individual skills.

## Publishing your own fork

If you fork or rename this repository, update the `source`, `homepage`, and `repository` fields
in [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json) and
[`.claude-plugin/plugin.json`](.claude-plugin/plugin.json) to point at your fork, and run
`claude plugin validate .` before publishing.

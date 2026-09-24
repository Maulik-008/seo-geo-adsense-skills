# Playbook: SEO Maintenance

## Purpose

Run a recurring SEO maintenance workflow using Search Console, analytics, page inventory, and Pagewell page conventions.

This skill operates the SEO system over time. It does not replace `qa.md`; it finds opportunities and maintenance tasks across the site.

## Required inputs

- `PAGEWELL.md`
- current page inventory or sitemap
- optional Google Search Console export
- optional analytics export
- optional keyword/rank tracking data
- optional list of priority products/pages

## Weekly checks

### Search Console performance

Look for:

- high impressions + low CTR
- average positions 11-20
- unexpected queries that suggest new pages
- traffic drops
- pages with impressions but no clicks

### Indexing

Look for:

- crawled but not indexed
- discovered but not indexed
- duplicate/canonical issues
- sitemap submitted vs indexed mismatch

### Internal links

- run or recommend `seo-ops.md internal-link subroutine`
- add links from ranking pages to priority pages when relevant

## Monthly checks

- add new FAQ page briefs from real questions
- add new glossary page briefs from recurring terms
- add new use-case page briefs from long-tail workflow queries
- improve low CTR titles with `seo-ops.md title-CTR subroutine`
- identify candidates for free tools
- update stale dates/year modifiers if used
- review competitor/alternative gaps

## Quarterly checks

- title audit across all indexable pages
- prune/merge/redirect pages with no traffic and no strategic value
- technical SEO review: sitemap, robots, schema, mobile, performance
- topic cluster coverage review
- backlink/partner opportunities

## Candidate actions

| Finding | First action | Escalation |
|---|---|---|
| High impressions, low CTR | optimize title/meta | test new angle/title |
| Position 11-20 | add internal links + improve page | create supporting FAQ/glossary pages |
| Crawled not indexed | improve internal links/uniqueness | consider republishing after waiting period |
| Unexpected query | create page brief | add to topic cluster |
| Orphan page | add contextual links | merge or remove if not useful |

## Output

```md
# SEO Maintenance Report

Date: YYYY-MM-DD

## Summary
- ...

## Opportunities
| Priority | Route/Query | Finding | Recommended Skill | Action |
|---:|---|---|---|---|

## Page briefs to create
...

## Fixes applied
- ...

## Next review
- ...
```

## Rules

- Do not mass-generate pages from weak signals.
- Prefer data-backed page ideas from impressions, queries, support questions, and real ICP workflows.
- Do not republish pages before title/meta/internal-link fixes unless the page is clearly stuck.
- Keep all recommendations tied to specific routes or queries.

## Acceptance criteria

- Report prioritizes actions.
- Recommendations name the next Pagewell skill to run.
- New page ideas include enough information to become briefs.

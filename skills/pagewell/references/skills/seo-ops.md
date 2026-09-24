# Skill: SEO Ops

## Purpose

Operate the SEO system over time: title CTR optimization, internal linking, Search Console maintenance, and safe stuck-page republishing.

This skill is for ongoing improvement. It does not replace `references/skills/qa.md`, which checks page quality before/after changes.

## Required inputs

- `PAGEWELL.md`
- current page inventory or sitemap
- optional Google Search Console export
- optional analytics export
- optional keyword/rank tracking data
- optional priority products/pages
- optional topic cluster plan

## Modes

### Title CTR optimization

Detailed playbook: `references/playbooks/seo/title-ctr.md`.

Use when:

- pages have high impressions but low CTR
- titles append brand unnecessarily
- titles are duplicated or vague
- page title does not match search intent

Rules:

- non-homepage SEO pages usually avoid brand suffixes
- primary keyword/search intent goes near the front
- title must be truthful and not clickbait
- roughly 30-60 characters where practical

### Internal-link audit

Detailed playbook: `references/playbooks/seo/internal-linking.md`.

Use when:

- new pages are launched
- a topic cluster is planned
- important pages are orphaned or weakly linked
- ranking pages should pass authority to priority pages

Check:

- orphan pages
- hub/supporting page links
- related FAQ/glossary/tool links
- broken links and redirect chains

### Maintenance report

Detailed playbook: `references/playbooks/seo/maintenance.md`.

Weekly checks:

- high impressions + low CTR
- positions 11-20
- unexpected queries
- indexing issues
- traffic drops

Monthly checks:

- new FAQ/glossary/use-case briefs
- title/meta rewrites
- free tool candidates
- competitor/alternative gaps
- internal link improvements

### Republish stuck page

Detailed playbook: `references/playbooks/seo/republish-stuck-page.md`.

Use only when normal fixes have not worked:

- crawled but not indexed for 4+ weeks
- stuck positions 11-30 for 4+ weeks
- meaningful impressions but very low clicks after title/meta/internal-link fixes

Requires explicit old URL handling:

- 301 redirect
- canonical to new URL
- noindex old page
- keep both only for genuinely different intents

## Output

Return the relevant report for the selected mode:

```md
# SEO Ops Report

Mode: title-ctr | internal-link-audit | maintenance | republish-stuck-page
Status: PASS | PASS WITH NOTES | FAIL | PLANNED

## Findings
- ...

## Actions applied
- ...

## Recommended next actions
- ...
```

## Rules

- Do not mass-generate pages from weak signals.
- Prefer data-backed actions from Search Console, analytics, support questions, or real ICP workflows.
- Do not republish pages before title/meta/internal-link fixes unless clearly justified.
- Keep recommendations tied to specific routes or queries.
- Do not create duplicate URLs for the same intent without canonical/redirect strategy.

## Acceptance criteria

- The selected mode is clear.
- Findings are prioritized.
- Changes preserve SEO safety and site conventions.
- Follow-up actions name the next Pagewell skill when applicable.

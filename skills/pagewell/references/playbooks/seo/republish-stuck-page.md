# Playbook: Republish Stuck Page

## Purpose

Safely republish an underperforming page under a new URL when a page appears stuck in indexing or rankings after normal fixes.

This is an advanced SEO tactic and should not be used casually. The goal is fresh evaluation without creating duplicate-content clutter.

## Required inputs

- `PAGEWELL.md`
- old route/page file
- performance/indexing evidence
- reason for republishing
- proposed new route
- canonical/redirect decision

## When to use

Use only when one or more is true:

- page is crawled but not indexed for 4+ weeks
- page is stuck around positions 11-30 for 4+ weeks
- page has meaningful impressions but very low clicks after title/meta fixes
- page has been improved and internally linked but still underperforms

## Do before republishing

1. Run `qa.md`.
2. Run or apply `seo-ops.md title-CTR subroutine`.
3. Add contextual internal links from relevant pages.
4. Check for duplicate/canonical issues.
5. Wait long enough for recrawl unless urgency is justified.

## Process

1. Record evidence for the old page.
2. Create a new route with a more specific/search-aligned slug.
3. Update content enough to be a real improvement:
   - better title/meta
   - clearer direct answer
   - improved examples/FAQ/internal links
   - fresher structure
4. Decide old URL handling:
   - `301 redirect` if the old page has no value and replacement is equivalent
   - `canonical to new URL` if old must remain temporarily
   - `noindex` old page if keeping it for users but not search
   - keep both only if they target genuinely different intents
5. Update internal links to point to the new URL where appropriate.
6. Update sitemap to include only the canonical/indexable URL.
7. Submit new URL in Search Console when applicable.

## Output

```md
# Republish Stuck Page

Old URL: ...
New URL: ...
Status: PLANNED | IMPLEMENTED | NEEDS APPROVAL

## Evidence
- ...

## Changes made
- ...

## Old URL handling
- ...

## Follow-up date
- ...
```

## Rules

- Do not mass-republish pages.
- Do not create multiple URLs for the same intent without canonical/redirect strategy.
- Do not use this to bypass poor content quality or weak internal linking.
- Preserve backlinks when they exist; prefer 301 when replacing an old URL.

## Acceptance criteria

- New URL has clearer search intent than the old URL.
- Old URL handling is explicit.
- Sitemap and internal links are updated.
- Page passes `qa.md`.

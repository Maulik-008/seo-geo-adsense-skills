# Playbook: Internal Link Audit

## Purpose

Audit and improve internal linking across generated and existing pages.

Internal links help users navigate related content and help authority flow from stronger pages to newer or priority pages.

## Required inputs

- `PAGEWELL.md`
- current route/page inventory
- sitemap if present
- product/company facts
- priority pages or cluster plan if available
- optional analytics/Search Console data

## Checks

### Orphan pages

- Indexable pages with no internal links pointing to them.
- Important pages missing from navigation, hub pages, related sections, or cluster links.

### Cluster links

For each topic cluster:

- hub/product page links to supporting pages
- supporting pages link back to hub/product page
- FAQs link to relevant glossary/use-case/tool pages
- glossary terms link to product/use-case/tool pages
- free tools link to product and related tools/use cases

### Priority link flow

- top-performing pages link to priority pages where contextually relevant
- high-intent pages link to conversion pages
- old pages link to new related pages

### Broken/internal redirects

- internal links should not 404
- internal links should avoid unnecessary redirect chains
- private/noindex pages should not be linked from public navigation unless intentional

## Process

1. Build or infer a page inventory.
2. Identify indexable vs noindex/private pages.
3. Identify current internal links where possible.
4. Find orphan pages and weakly linked pages.
5. Recommend contextual links by source page and target page.
6. Implement small, obvious link additions when in scope.
7. Report any larger changes for approval.

## Output

```md
# Internal Link Audit

Status: PASS | PASS WITH NOTES | FAIL

## Orphan pages
- ...

## Recommended links
| Source | Target | Anchor text | Reason |
|---|---|---|---|

## Fixes applied
- ...

## Follow-up
- ...
```

## Rules

- Links should be contextually useful, not stuffed.
- Use descriptive anchor text.
- Do not create sitewide footer spam.
- Do not publicly link private/ABM pages unless the brief explicitly says to.
- Preserve existing navigation conventions.

## Acceptance criteria

- Priority/indexable pages have at least one relevant internal link.
- New generated pages are not orphaned.
- Related pages within a cluster link to each other naturally.

# Skill: QA

## Purpose

Review generated or modified pages for routing, metadata, SEO/GEO, design consistency, schema, sitemap behavior, conversion, and factual correctness.

This skill also contains the claim-check subroutine for comparison/alternative and other high-risk pages.

Detailed claim playbook: `references/playbooks/qa/claim-check.md`.

## Inputs

- `PAGEWELL.md`
- validated `DESIGN.md`
- page brief/spec if available
- generated/modified page files
- discovery files if changed
- optional build/test commands

## Checks

### Routing

- Requested route exists.
- Route matches site conventions.
- Page can be built/rendered by the site's build system where possible.
- Private pages are not added to public navigation.

### Metadata

- Unique title.
- Unique meta description.
- One H1.
- Canonical URL for indexable pages.
- `noindex,nofollow` for private pages.
- Non-homepage SEO titles avoid unnecessary brand suffixes unless brand is part of the query.
- Open Graph/Twitter tags where site supports them.

### Schema

- JSON-LD is valid JSON.
- `FAQPage` schema only appears when visible FAQ exists.
- FAQ schema questions/answers match visible copy.
- `SoftwareApplication` facts are supported by `PAGEWELL.md` product facts.
- `WebApplication` schema is present for indexable free tools.
- `DefinedTerm` facts are supported by glossary content.
- `BreadcrumbList` URLs are correct.

### Discovery

- Indexable pages appear in sitemap if the site maintains a sitemap.
- `noindex` pages do not appear in sitemap.
- `robots.txt` does not block indexable pages.
- `llms.txt` remains factual if updated.

### Design

- `DESIGN.md` has zero linter errors when validation is possible.
- Page follows `DESIGN.md` tokens and prose.
- Existing components/layouts are reused where possible.
- No new visual system, random colors, or inconsistent spacing.
- Mobile behavior follows existing site conventions.

### Content and claims

- Product claims come from `PAGEWELL.md` supported claims, product facts, or the brief.
- No invented metrics, customers, testimonials, ratings, prices, or integrations.
- Page answers its stated intent directly.
- FAQ pages answer one exact question and avoid near-duplicate intent.
- Glossary pages define one term clearly and include an example/application when useful.

### Genericness

Fail or warn when:

- The page could describe any SaaS product after swapping the product name.
- Headings are generic labels such as `Problem`, `Solution`, or `Benefits` without intent-specific context.
- The page lacks product-specific mechanics from `PAGEWELL.md`.
- The page lacks a concrete workflow, example, command, comparison dimension, or tool output where relevant.
- The section order mechanically mirrors the playbook instead of adapting to the route intent and site page patterns.
- The CTA is generic or mismatched to audience/intent.

### Claim-check subroutine

Run this for:

- alternative/comparison pages
- competitor mentions
- security/compliance claims
- performance or revenue claims
- customer/testimonial/logos
- any claim that sounds like a superlative

Classify claims as:

- supported by `PAGEWELL.md` product facts
- provided by brief
- generic/low-risk
- unsupported

Rewrite or remove unsupported claims. Prefer “when to choose X/Y” framing for comparisons.

### Conversion

- Primary CTA exists.
- Product command/copy UI exists if applicable.
- Outbound links are correct.
- Contact/email links are correct.

### Free tool pages

For `pageType: free-tool`:

- Tool provides a useful result without authentication.
- Tool interface is visible above the fold or immediately after the hero.
- Inputs have labels, validation, and helpful errors.
- Output has copy/download/share action where relevant.
- Lead capture, if present, does not block first value.
- `WebApplication` schema is present for indexable tool pages.
- `offers.price` is `0` when claiming the tool is free.
- Tool usage/product CTA events follow existing analytics conventions if analytics exists.

## Output

Return a concise QA report:

```md
# QA Report: <route>

Status: PASS | PASS WITH NOTES | FAIL

## Checked files
- ...

## Findings
- [pass] ...
- [warn] ...
- [fail] ...

## Claim check
- ...

## Required fixes
- ...

## Suggested improvements
- ...
```

## Rules

- If a build/test command exists and is safe, run it.
- Do not silently ignore failures.
- Prefer fixing small issues immediately when in scope.
- Ask before broad refactors.

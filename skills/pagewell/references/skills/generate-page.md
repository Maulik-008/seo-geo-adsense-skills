# Skill: Generate Page

## Purpose

Generate or update a framework-agnostic website page from a page brief.

This single skill handles standard page types through page-type playbooks. Free tools have their own specialized skill because they require a working utility interface.

## Required inputs

- `PAGEWELL.md`
- validated `DESIGN.md`
- page brief with `pageType`, route, title, description, H1, intent, CTA, and constraints

## Supported page types

| pageType | Playbook |
|---|---|
| `product` | `references/playbooks/page-types/product.md` |
| `use-case` | `references/playbooks/page-types/use-case.md` |
| `faq` | `references/playbooks/page-types/faq.md` |
| `glossary` | `references/playbooks/page-types/glossary.md` |
| `alternative` | `references/playbooks/page-types/alternative.md` |
| `docs` | `references/playbooks/page-types/docs.md` |
| `lp` | `references/playbooks/page-types/lp.md` |
| `private` | `references/playbooks/page-types/private.md` |
| `custom` | infer closest existing pattern, then ask if unclear |

For `free-tool` and `tools-hub`, use `references/skills/generate-free-tool.md`.

## Framework-neutral process

1. Read `PAGEWELL.md`, including product facts, claim rules, site implementation, route taxonomy, page/component patterns, generation rules, and anti-generic QA rules.
2. Read `DESIGN.md` and follow its tokens/prose.
3. Read the page brief.
4. Select the matching page-type playbook.
5. Create a page architecture/evidence map that adapts playbook coverage to the site's patterns. Section labels are coverage requirements, not literal headings or fixed order.
6. Create a framework-neutral page spec:
   - route
   - pageType
   - title
   - description
   - H1
   - noindex/nofollow
   - sections
   - schema
   - related links
   - CTA
7. Implement using the current site's conventions:
   - Astro: content collection or `src/pages`
   - Next.js: `app/` or `pages/`
   - Cloudflare Worker: page registry/render helper
   - Static HTML: route folder with `index.html`
   - Unknown: mirror existing route patterns
8. Run or recommend `references/skills/qa.md`.
9. Run or recommend `references/skills/update-discovery-files.md` when indexability changes.

## Universal requirements

Every indexable generated page should have:

- unique title
- unique meta description
- one H1
- canonical URL
- crawlable HTML content
- relevant internal links
- schema only when supported by visible content/facts
- design consistent with `DESIGN.md`
- page/component patterns consistent with `PAGEWELL.md`
- specific, non-generic copy that uses verified product mechanics and evidence

## Page-type guardrails

### Product

- Use canonical `PAGEWELL.md` product facts.
- Explain what the product is, who it is for, and how it works.
- Include product command/demo when available.

### Use case

- Target a specific workflow/scenario.
- Use problem → solution → step-by-step → benefits.
- Include concrete commands/examples when available.

### FAQ

- One searched question per URL.
- H1 is the exact question.
- First sentence answers directly.

### Glossary

- One term per URL.
- Include clear one-line definition and example/application.
- Use `DefinedTerm` schema when supported.

### Alternative/comparison

- Be factual and fair.
- Run claim checks in `references/skills/qa.md`.
- Use “when to choose X/Y” framing.

### Docs

- Command-forward and task-oriented.
- Do not invent flags, APIs, or expected outputs.

### LP

- Conversion-focused.
- One primary CTA.
- Default to `noindex` for temporary/paid campaign pages unless brief says durable SEO.

### Private

- Always `noindex,nofollow`.
- Exclude from sitemap and public navigation.
- Do not invent account facts.

## Anti-generic requirements

Before implementation and again during QA, check:

- Could this page describe any SaaS product after swapping the product name?
- Are headings adapted to the specific intent instead of generic labels like `Problem`, `Solution`, or `Benefits`?
- Does the page use product-specific mechanics from `PAGEWELL.md`?
- Does it include a concrete workflow, example, command, comparison dimension, or decision aid where relevant?
- Does the CTA match the page's audience and intent?

## Acceptance criteria

- Page exists at requested route.
- It follows the correct page-type playbook.
- It follows current framework conventions.
- It uses `PAGEWELL.md` product facts and avoids unsupported claims.
- It passes `references/skills/qa.md`.

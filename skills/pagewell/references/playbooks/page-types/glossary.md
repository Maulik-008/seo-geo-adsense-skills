# Playbook: Glossary Page

## Purpose

Generate an individual glossary/definition page for a domain term your ICP searches for.

Glossary pages build topical authority, explain vocabulary, and link readers into relevant product, docs, use-case, and free-tool pages.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief with term, definition, examples, related terms, CTA, and route

## Framework-neutral page spec

```yaml
route: /glossary/<term-slug>
pageType: glossary
title: <Term> - Definition, Examples & How to Use
description: <Term> is <one-line definition>. Learn examples and how it applies.
h1: What is <Term>?
primaryKeyword: <term> definition
product: <product-slug optional>
noindex: false
sections:
  - definition
  - expanded-explanation
  - example
  - how-to-use
  - related-terms
  - related-links
  - cta
schema:
  - DefinedTerm
  - BreadcrumbList
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Label or eyebrow: `Definition`.
2. H1: `What is <Term>?` or `<Term>: Definition and Examples`.
3. One-line definition at the top.
4. Expanded explanation.
5. Practical example, code snippet, screenshot, or mini workflow where useful.
6. Related terms/internal links.
7. Product/tool CTA when natural.

## Content rules

- Define the term plainly before selling anything.
- Prefer 250-700 words, but do not pad.
- Include examples for technical terms whenever possible.
- Use product references as application context, not as a replacement for the definition.
- Avoid defining terms outside the site's real domain.

## Title rules

Recommended patterns:

```txt
<Term> - Definition, Examples & How to Use
What Is <Term>? Definition & Examples
```

Do not append the brand name to non-homepage titles unless the brand is part of the query.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing route/content conventions.
- Reuse article, code, CTA, and related-link components.
- If a glossary index exists, add this term to it; otherwise note that `generate-glossary-index` or a generic index may be useful.

## SEO/GEO rules

- Use the term in title, H1, first paragraph, and at least one subheading where natural.
- Include canonical URL.
- Add `DefinedTerm` JSON-LD when supported by the site's schema conventions.
- Link to related glossary terms and relevant product/use-case/free-tool pages.
- Add to sitemap when indexable.

## Acceptance criteria

- Page exists at the requested route.
- It defines the term directly and accurately.
- It includes an example or concrete application when useful.
- It links to related terms/pages.
- It passes `qa.md`.

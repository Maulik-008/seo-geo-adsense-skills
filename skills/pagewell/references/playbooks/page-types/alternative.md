# Playbook: Alternative or Comparison Page

## Purpose

Generate a factual, high-intent alternative/comparison page.

These pages should help users decide between options without inventing competitor claims.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- competitor/alternative facts supplied by user or verified from source
- page brief with route, primary keyword, audience, CTA, and comparison scope

## Framework-neutral page spec

```yaml
route: /alternatives/<competitor-or-alternative-slug>
pageType: alternative
title: <Product> Alternative to <Competitor/Alternative> | <Site>
description: <factual positioning summary>
h1: <Product> alternative to <Competitor/Alternative>
product: <product-slug>
comparisonTarget: <name>
noindex: false
sections:
  - hero
  - decision-summary
  - what-each-option-is
  - comparison-table
  - when-to-choose-product
  - when-to-choose-alternative
  - faq
  - related-links
  - cta
schema:
  - WebPage
  - BreadcrumbList
  - FAQPage
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Hero with target keyword.
2. Short decision summary.
3. What each product/alternative is for.
4. Factual comparison table.
5. When to choose the site product.
6. When to choose the other option.
7. FAQ.
8. Related links.
9. CTA.

## Claim rules

Run `references/skills/qa.md` with the claim-check subroutine before finalizing.

- Do not invent competitor features, pricing, customers, metrics, or weaknesses.
- Do not say "best" unless the brief provides a defensible source.
- Use "may", "is better suited for", and "choose X when" language where appropriate.
- Acknowledge the alternative's strengths when known.
- If facts are unknown, say less rather than fabricate.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing routing/content conventions.
- Reuse existing comparison table or card components where present.
- Preserve design from `DESIGN.md`.

## SEO/GEO rules

- Use target query in title/H1/intro.
- Include canonical URL.
- Include FAQ schema only for visible FAQs.
- Add links to product and relevant use-case pages.

## Acceptance criteria

- Page is factual and non-defamatory.
- Comparison table only includes verified or clearly scoped claims.
- Page passes `references/skills/qa.md`, including the claim-check subroutine.

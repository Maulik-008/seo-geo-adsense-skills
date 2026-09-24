# Playbook: LP / Campaign Page

## Purpose

Generate a conversion-focused landing page for paid ads, campaigns, launches, or experiments.

LP pages optimize message match and conversion. They may be indexable, but should be `noindex` if they are duplicate, temporary, personalized, or campaign-only.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief with route, campaign, audience, offer, CTA, traffic source, and index/noindex decision

## Framework-neutral page spec

```yaml
route: /lp/<slug>
pageType: lp
title: <campaign-specific title>
description: <campaign-specific description>
h1: <campaign-specific promise>
product: <product-slug>
noindex: <true|false>
sections:
  - hero
  - pain-promise
  - proof-or-demo
  - benefits
  - how-it-works
  - faq
  - cta
schema:
  - WebPage
  - FAQPage
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Focused hero with one primary CTA.
2. Message match to ad/source/audience.
3. Product command/demo/proof block.
4. Benefits tied to the campaign's pain.
5. Short how-it-works.
6. FAQ only if useful for conversion.
7. Final CTA.

## Conversion rules

- One primary CTA.
- Reduce unnecessary navigation when the site convention allows.
- Keep above-the-fold CTA visible.
- Preserve UTM/query parameters when linking onward if the site has link helpers.
- Include copy/install button when product has a command.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow route/content conventions.
- Reuse components and design tokens.
- Do not make the page visually inconsistent with the site.

## SEO/indexing rules

- Default to `noindex` for temporary paid pages unless the brief says it is a durable SEO page.
- Exclude `noindex` LP pages from sitemap.
- Use canonical URL when indexable.

## Acceptance criteria

- Route exists.
- One clear CTA.
- Index/noindex behavior matches the brief.
- Page passes `qa.md`.

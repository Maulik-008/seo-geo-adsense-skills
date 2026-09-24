# Playbook: Private / ABM Page

## Purpose

Generate a personalized outbound, sales follow-up, or account-based marketing page.

Private pages are for direct sharing, not SEO.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief with target account/persona/context, route, CTA, and allowed personalization facts

## Framework-neutral page spec

```yaml
route: /private/<slug>
pageType: private
noindex: true
nofollow: true
title: <private page title>
description: <private description>
h1: <personalized headline>
sections:
  - personalized-hero
  - account-context
  - proposed-workflow
  - why-this-product
  - next-step
schema: []
```

## Required behavior

- Always include `<meta name="robots" content="noindex,nofollow">` or the site's equivalent.
- Never include private pages in sitemap.
- Do not add private pages to public navigation.
- Avoid sensitive/private data unless explicitly provided in the brief.


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Personalized hero.
2. Context based only on supplied facts.
3. Relevant problem/workflow.
4. Why the product fits.
5. Clear next step/contact CTA.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow routing conventions.
- Reuse existing layout/components unless a simplified private layout exists.

## Acceptance criteria

- Page is reachable only by URL.
- It is noindex,nofollow.
- It is absent from sitemap and public nav.
- It contains no invented account facts.
- It passes `qa.md`.

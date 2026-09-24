# Playbook: Tools Hub

## Purpose

Generate or update a `/tools` hub that lists all durable free tools on the site.

The tools hub improves internal linking, helps users discover related utilities, and gives search engines a stable index of utility pages.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- list of existing or planned free tool pages

## Framework-neutral page spec

```yaml
route: /tools
pageType: tools-hub
title: Free <Category> Tools | <Brand>
description: A collection of free tools for <ICP/use case>. No signup required.
h1: Free <category> tools
noindex: false
sections:
  - hero
  - tool-grid
  - categories-or-filters
  - product-cta
  - faq
schema:
  - CollectionPage
  - BreadcrumbList
  - FAQPage
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Hero explaining who the tools are for.
2. Tool cards with name, description, category, and link.
3. Category filters if there are 10+ tools or multiple product areas.
4. CTA to main product/company.
5. FAQ.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing route/content conventions.
- Reuse card/grid components.
- Include only indexable, public free tools.
- Exclude private/noindex tools.

## Acceptance criteria

- `/tools` exists.
- It links to all public free tools.
- It has unique metadata and canonical URL.
- It is included in sitemap when indexable.

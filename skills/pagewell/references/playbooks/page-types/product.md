# Playbook: Product Page

## Purpose

Generate or update a durable product landing page for a specific product.

Product pages are indexable, canonical product/entity pages. They should explain what the product is, who it is for, how it works, and what action to take next.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief or user request naming the product

## Framework-neutral page spec

Before implementing, form a page spec like:

```yaml
route: /products/<product-slug>
pageType: product
title: <Product Name> | <Site Name>
description: <concise product value proposition>
h1: <Product Name>
product: <product-slug>
noindex: false
sections:
  - hero
  - direct-answer
  - who-it-is-for
  - problem
  - solution
  - how-it-works
  - command-or-demo
  - use-cases
  - faq
  - related-links
  - cta
schema:
  - WebPage
  - SoftwareApplication
  - BreadcrumbList
  - FAQPage
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Hero with product name, one-sentence value proposition, and primary CTA.
2. Direct answer: "What is <Product>?"
3. Who it is for.
4. Problem the product solves.
5. How the product solves it.
6. Install command/demo block if relevant.
7. Use cases.
8. FAQ.
9. Related internal links.
10. Final CTA.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing routing, layout, component, and metadata conventions.
- If the site uses components, reuse them.
- If the site uses content files, create content; if it uses route files, create route files; if it uses a page registry, register the page.
- Use `PAGEWELL.md` product facts exactly; do not invent capabilities.

## SEO/GEO rules

- Unique title and description.
- One H1.
- Canonical URL.
- Open Graph and Twitter metadata if site supports them.
- `SoftwareApplication` JSON-LD when enough facts exist.
- `FAQPage` JSON-LD only if FAQ is visible on page.
- Internal links to related use-case and alternative pages.

## Acceptance criteria

- Product page is reachable at the requested route.
- Copy uses canonical `PAGEWELL.md` product facts.
- Primary CTA is visible above the fold.
- Install command/copy UI exists if product has a command.
- Page passes `qa.md`.

# Playbook: Use-Case Page

## Purpose

Generate an indexable SEO/GEO page for a real job-to-be-done or search intent.

Use-case pages should give a clear answer, explain the problem, map the product to the use case, and convert readers with a relevant CTA.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief with route, keyword/intent, audience, product, CTA, and constraints

## Framework-neutral page spec

```yaml
route: /use-cases/<slug>
pageType: use-case
title: <Use Case or Primary Keyword> - <Key Benefit>
description: <direct benefit in under ~160 chars>
h1: <Primary keyword>
primaryKeyword: <keyword>
product: <product-slug>
noindex: false
sections:
  - hero
  - direct-answer
  - problem
  - pain-points
  - solution
  - step-by-step-workflow
  - benefits
  - examples-or-use-cases
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

1. H1 with the specific workflow or primary keyword.
2. Short direct answer/problem statement in the first screen.
3. Problem section.
4. Specific pain points.
5. How the product solves the problem.
6. Step-by-step workflow, including commands/examples when relevant.
7. Benefits.
8. Practical use cases or examples.
9. FAQ section.
10. Internal links.
11. CTA.

## Content rules

- The page must satisfy the query directly, not just sell.
- Target a specific workflow/scenario, not a vague category.
- Use problem → solution → step-by-step → benefits structure.
- Use the product as the solution only where it naturally fits.
- Include commands, examples, screenshots, or concrete workflows when available.
- Avoid thin or duplicative pages; if there is not enough substance, ask for more input instead of generating.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing route/content conventions.
- Reuse existing components and layout.
- Do not create a new design language.

## SEO/GEO rules

- Use the primary keyword in title, H1, intro, and at least one subheading where natural.
- Recommended title pattern: `<Use Case> - <Key Benefit>`.
- Do not append the brand to non-homepage titles unless the brand is part of the query.
- Include canonical URL.
- Include visible FAQ and matching FAQ schema when relevant.
- Add related internal links to product, adjacent use-case, and alternative pages.
- Keep copy factual and citation-friendly.

## Acceptance criteria

- Page exists at requested route.
- It answers the intent within the first 150 words.
- It links to the product page and at least one related page where available.
- It passes `qa.md`.

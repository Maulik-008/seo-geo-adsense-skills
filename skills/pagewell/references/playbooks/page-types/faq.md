# Playbook: FAQ Page

## Purpose

Generate an individual FAQ page for one specific searched question.

FAQ pages are topical-authority pages. Each page should answer one question directly, link to related pages, and route qualified readers toward the relevant product or tool.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief with route, exact question, short answer, product/context, CTA, and related questions/pages

## Framework-neutral page spec

```yaml
route: /faq/<question-slug>
pageType: faq
title: <Question> - <Short Answer Phrase>
description: <direct answer in ~150 chars plus solution mention>
h1: <Exact question people search>
primaryKeyword: <question keyword>
product: <product-slug optional>
noindex: false
sections:
  - direct-answer
  - expanded-answer
  - example-or-steps
  - related-questions
  - related-links
  - cta
schema:
  - WebPage
  - FAQPage
  - BreadcrumbList
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. H1 written as the exact searched question.
2. First sentence gives the direct answer.
3. 2-4 short paragraphs expanding the answer.
4. Optional steps, example, code, or command when useful.
5. Related questions/internal links.
6. Product/tool CTA when natural.

## Content rules

- Answer exactly one question.
- Keep the page focused. Short is acceptable when the answer is complete.
- Prefer 150-500 words, but do not pad.
- Use the product only where relevant.
- Do not create near-duplicate FAQ pages with tiny wording changes.
- If the answer depends on unverified product behavior, ask for facts or mark uncertainty.

## Title rules

Use the `seo-ops.md title-CTR subroutine` skill if title quality is uncertain.

Recommended pattern:

```txt
<Question> - <Short Answer Phrase>
```

Examples:

```txt
How to Share Markdown from Terminal - Free CLI Tool
What Is Mermaid Syntax - Diagram Definition Examples
```

Do not append the brand name to non-homepage titles unless the brand is part of the query.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing route/content conventions.
- Reuse existing article, FAQ, CTA, and related-link components.
- If the site already has a FAQ section, do not replace it; create an individual URL for the specific question.

## SEO/GEO rules

- Use the exact question in H1.
- Put the direct answer in the first 1-2 sentences.
- Include canonical URL.
- Include `FAQPage` schema only if the visible page has the same question/answer.
- Add internal links to product, glossary, use-case, docs, or free-tool pages where relevant.
- Add to sitemap when indexable.

## Acceptance criteria

- Page exists at the requested route.
- It answers one question directly.
- It has unique title/description.
- It links to related questions/pages where available.
- It passes `qa.md`.

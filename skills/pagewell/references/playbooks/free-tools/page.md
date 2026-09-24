# Playbook: Free Tool Page

## Purpose

Generate a working free utility page that drives SEO/GEO traffic, provides immediate value, and creates a natural path to the main product.

Free tool pages are indexable by default when durable and useful. They should be more than content pages: the tool must actually work.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- page brief with route, target keyword, product, tool spec, CTA, and indexing decision

## Framework-neutral page spec

```yaml
route: /tools/<slug>
pageType: free-tool
title: <Tool Name> - Free <Utility> | <Brand>
description: <150-160 char description with keyword and no-signup value>
h1: <Tool name with target keyword>
primaryKeyword: <keyword>
product: <product-slug>
noindex: false
tool:
  category: generator | converter | analyzer | calculator | previewer | validator | other
  input:
    - name: <field>
      type: text | textarea | number | select | file | url
      required: true
  output:
    - name: <result>
      format: text | markdown | html | json | table | file | score
  logic: <deterministic transformation or API-backed behavior>
  privacy: <what happens to user input>
sections:
  - hero
  - tool-interface
  - how-to-use
  - examples
  - related-tools
  - product-cta
  - faq
schema:
  - WebApplication
  - FAQPage
  - BreadcrumbList
```


Section labels in this spec are coverage labels, not mandatory headings or fixed layout order. Adapt the final architecture to `PAGEWELL.md` page/component patterns and the route intent.

## Required coverage

1. Hero with target keyword and no-signup value proposition.
2. Working tool interface above the fold or immediately after hero.
3. Result area with copy/download/share action where relevant.
4. How to use section with simple steps.
5. Example inputs/outputs where useful.
6. Product CTA explaining the next step beyond the free tool.
7. Related tools/internal links.
8. FAQ section.
9. Lightweight powered-by/footer link to the main brand/product.

## Tool requirements

- The tool must provide value without signup.
- The primary action must be usable on page load.
- Prefer deterministic, client-side logic for v1.
- If server/API processing is required, explain why and follow existing backend conventions.
- Include validation and helpful errors.
- Include copy-to-clipboard for text outputs where useful.
- Avoid storing user input unless the brief explicitly requires it.

## Lead capture rules

Lead capture is optional and must not block first value.

Allowed:

- CTA after result generation.
- Email capture after repeated uses or time delay.
- "Powered by <brand>" link.
- Product CTA section.
- Share/copy buttons.

Not allowed:

- Signup wall before first result.
- Misleading "free" page that only captures email.
- Dark patterns that obscure or degrade the free tool.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- Follow existing route, component, styling, and metadata conventions.
- Reuse existing form, button, card, code, and layout components when present.
- Do not assume React/Next.js. If the site is Astro, Worker, static HTML, or custom, implement using that stack's conventions.
- If the stack cannot support interactivity without new dependencies, propose the smallest safe implementation path before adding packages.

## SEO/GEO rules

- Use target keyword in title, H1, intro, and URL slug.
- Title pattern: `<Tool Name> - Free <Utility> | <Brand>` when it fits under ~60 chars.
- Include canonical URL.
- Include `WebApplication` JSON-LD with `offers.price = 0` when indexable.
- Include visible FAQ and matching `FAQPage` schema.
- Include a tools hub link if `/tools` exists or is being created.
- Add page to sitemap if indexable.
- Include in `llms.txt` only if the tool is durable and important.

## Analytics rules

When the site has analytics/event conventions, track:

- `free_tool_used`
- `free_tool_result_copied`
- `free_tool_product_cta_clicked`
- `free_tool_email_submitted` if email capture exists

Do not add a new analytics provider without approval.

## Acceptance criteria

- Page exists at requested route.
- Tool works without authentication.
- First useful result is available without signup.
- Page has correct metadata, canonical, and WebApplication schema when indexable.
- Page includes how-to-use, FAQ, related/internal links, and product CTA.
- Page passes `qa.md`.

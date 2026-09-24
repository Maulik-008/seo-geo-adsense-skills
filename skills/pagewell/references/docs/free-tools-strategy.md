# Free Tools Strategy

Free tools are a Pagewell acquisition pattern: small utilities that rank for practical queries, create trust through immediate value, and route qualified users toward a product.

## Philosophy

A free tool should be useful even if the visitor never signs up.

The ideal free tool:

- solves one narrow problem
- works immediately
- requires no signup before first value
- targets a query people already search
- is related to the product's domain
- has a natural product CTA
- is cheap to build and maintain

## Common tool types

| Type | Examples |
|---|---|
| Generator | README generator, prompt generator, title generator |
| Converter | Markdown to HTML, JSON to CSV, CSV to markdown table |
| Analyzer/checker | schema checker, landing page grader, robots.txt checker |
| Calculator | ROI calculator, pricing calculator, usage estimator |
| Previewer | markdown preview, OG image preview, Mermaid preview |
| Validator | URL validator, JSON validator, llms.txt validator |

## Workflow

1. Analyze product and ICP.
2. Brainstorm 15 ideas.
3. Score ideas on search intent, build speed, product fit, uniqueness, and utility.
4. Select the top 3.
5. Generate the first tool page.
6. QA for SEO, schema, usefulness, and no-signup behavior.
7. Launch immediately through social/community channels.
8. Track usage and iterate.

## Required coverage

Every durable free tool page should cover these jobs, adapted to `PAGEWELL.md` page patterns:

- keyword-focused H1
- working tool interface
- result output with copy/download/share if relevant
- how-to-use section
- example input/output when useful
- FAQ
- related tools/internal links
- product CTA
- WebApplication schema

## Lead capture

Lead capture must not block first value.

Good:

- CTA after result generation
- optional email prompt after repeated uses
- product CTA in page body
- powered-by link

Bad:

- signup wall before first use
- fake tool that only captures email
- intrusive popup before the user understands value

## Schema

Use `WebApplication` JSON-LD for indexable free tools:

```json
{
  "@context": "https://schema.org",
  "@type": "WebApplication",
  "name": "Tool Name",
  "description": "Tool description",
  "url": "https://example.com/tools/tool-slug",
  "applicationCategory": "UtilityApplication",
  "operatingSystem": "Any",
  "offers": {
    "@type": "Offer",
    "price": "0",
    "priceCurrency": "USD"
  }
}
```

Add `FAQPage` only when FAQ content is visible.

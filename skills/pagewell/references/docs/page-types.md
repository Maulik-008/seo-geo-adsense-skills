# Page Types

Pagewell supports a small set of durable page archetypes.

## Product page

Route pattern: `/products/<product>`

Purpose: canonical product/entity page.

Best for: product name searches, internal linking, product overview, conversion.

## Use-case page

Route pattern: `/use-cases/<job-or-intent>`

Purpose: answer a real job-to-be-done query and map it to a product.

Best for: SEO/GEO, long-tail search, product education.

## FAQ page

Route pattern: `/faq/<question>`

Purpose: answer one specific question people search for.

Best for: exact question intent, featured answers, and internal links into product/use-case/tool pages.

Required traits:

- H1 is the exact question
- first sentence answers directly
- one question per URL
- related questions/internal links
- FAQPage schema when visible answer matches JSON-LD

## Glossary page

Route pattern: `/glossary/<term>`

Purpose: define one domain term and connect it to examples, related concepts, and product workflows.

Best for: topical authority and definition queries.

Required traits:

- clear one-line definition
- expanded explanation
- concrete example where useful
- related terms/internal links
- DefinedTerm schema when supported

## Alternative/comparison page

Route pattern: `/alternatives/<target>` or `/compare/<a-vs-b>`

Purpose: help high-intent users decide between options.

Best for: factual product positioning. Requires claim checking.

## Free tool page

Route pattern: `/tools/<tool>`

Purpose: working, no-signup utility that targets a practical search query and creates trust before conversion.

Best for: SEO/GEO acquisition, backlinks, product-led lead capture, and community launches.

Required traits:

- immediate value without signup
- working input/output interface
- narrow search intent
- product-adjacent CTA
- WebApplication schema when indexable

## Tools hub

Route pattern: `/tools`

Purpose: index and internally link public free tools.

Best for: tool discovery, internal linking, and category-level SEO.

## LP/campaign page

Route pattern: `/lp/<campaign>`

Purpose: conversion-focused page for a campaign, ad, launch, or experiment.

Best for: paid traffic and message matching. Often `noindex`.

## Private/ABM page

Route pattern: `/private/<account>` or `/accounts/<account>`

Purpose: personalized outbound or sales follow-up.

Best for: direct sharing. Always `noindex,nofollow` and excluded from sitemap.

## Docs/tutorial page

Route pattern: `/docs/<task>`

Purpose: help users complete a technical task.

Best for: developer intent, support, AI citations.

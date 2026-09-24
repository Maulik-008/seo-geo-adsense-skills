# Skill: Define Product Facts

## Purpose

Create or normalize the canonical product/company facts and claim rules in `PAGEWELL.md`.

Generated pages must use `PAGEWELL.md` instead of inventing product claims. Standalone files such as `products.yaml` are legacy or optional data sources unless the user explicitly asks to maintain them.

## Inputs

- Existing `PAGEWELL.md` if present.
- Existing website content.
- Product websites/docs if available.
- User-provided product facts.
- Existing data files such as `products.ts`, `products.yaml`, `products.json`, `site.ts`, or CMS data.

## Preferred output

Update these sections in `PAGEWELL.md`:

```md
## Product facts

### Product
- Name:
- URL:
- Category:
- One-sentence description:
- Primary audience:
- Primary CTA:
- Secondary CTA:

### What the product does
- ...

### What the product does not do
- ...

## Supported claims

| Claim | Source | Confidence |
|---|---|---|

## Prohibited or unknown claims

- ...
```

If `PAGEWELL.md` does not exist, route to `references/skills/discover-site.md` so site context, page patterns, and product facts are created together.

If the user explicitly wants a standalone product file, create or update `products.yaml` using the existing format and also summarize the canonical facts in `PAGEWELL.md`.

## Required fields per product

- stable slug/key if multiple products exist
- name
- URL
- category
- one-sentence description
- audience
- primary CTA
- install command if applicable
- factual capabilities
- supported claims with source/confidence
- prohibited/unknown claims if useful

## Rules

- Do not invent claims, metrics, testimonials, customer names, prices, or integrations.
- If a fact is uncertain, mark it as unknown or prohibited until confirmed.
- Keep product descriptions consistent across pages.
- `PAGEWELL.md` product facts and supported claims are the truth source for generated page copy.
- Include source notes when a claim comes from a specific repo file, docs page, or user-provided source.

## Acceptance criteria

- `PAGEWELL.md` has enough product facts to generate product, use-case, LP, docs, free-tool, and alternative pages.
- Supported claims and prohibited/unknown claims are separated.
- Unverified claims are absent or explicitly marked unknown.

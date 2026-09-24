# Skill: Discover Site

## Purpose

Create or update `PAGEWELL.md`, the durable Pagewell context file for a repo/site.

`PAGEWELL.md` is the unified Pagewell source of truth for:

- product/company facts
- supported and prohibited claims
- site implementation conventions
- route taxonomy
- page/component patterns
- generation rules
- anti-generic QA rules
- QA rules

`DESIGN.md` remains separate because it follows the Google Labs Code `DESIGN.md` specification and is the visual identity contract.

Only create or update legacy `SITE_PROFILE.md` when the user explicitly asks for that file.

## When to use

Use this skill when:

- `PAGEWELL.md` does not exist.
- Pagewell is being run in a repo for the first time.
- The user asks to discover, inspect, detect, or document a site stack.
- Existing `SITE_PROFILE.md`, `products.yaml`, product data, or page-pattern notes need to be consolidated.
- Site implementation, route taxonomy, product facts, claim rules, or page patterns have changed.
- Generation feels generic because product facts, site conventions, and page patterns are scattered or missing.

## Inputs to inspect

Inspect what exists; do not assume all files are present.

### Existing Pagewell/design files

- `PAGEWELL.md`
- `DESIGN.md`
- legacy `SITE_PROFILE.md`
- `products.yaml`, `products.yml`, `products.json`, `src/data/products.*`, `site.ts`, `src/lib/seo.*`, or equivalent product/company data

### Repo and framework files

- `package.json`
- `astro.config.*`
- `next.config.*`
- `remix.config.*`
- `svelte.config.*`
- `vite.config.*`
- `wrangler.toml`
- `worker.js`, `src/worker.*`, `functions/`
- `src/pages/`, `src/app/`, `app/`, `pages/`, `routes/`
- `src/content/`, `content/`, `data/`, `src/data/`
- `src/components/`, `components/`
- `src/layouts/`, `layouts/`
- `public/`, `static/`
- existing `robots.txt`, `sitemap.xml`, `llms.txt`
- deployment configs: Cloudflare Pages, Workers, Vercel, Netlify, GitHub Actions

### Marketing/product surfaces

- homepage and main route files
- docs, README, landing pages, pricing pages, customer pages, comparison pages, and public examples
- existing generated pages or content collections
- testimonials, customer logos, metrics, pricing, integrations, and claims only when visible in the repo or user-provided sources

## Detection hints

- Astro: `astro.config.*`, `src/pages`, `.astro` files.
- Next.js App Router: `next.config.*`, `app/**/page.*`.
- Next.js Pages Router: `pages/*.tsx`, `pages/_app.*`.
- Cloudflare Worker: `wrangler.toml`, `worker.js`, `export default { async fetch(request) { ... } }`.
- Vite SPA/static: `vite.config.*`, `index.html`, `src/main.*`.
- Plain static: route folders with `index.html` and no framework config.
- Custom: infer from routing/build scripts and existing file patterns.

## Process

1. Check whether `DESIGN.md` exists.
   - If missing, document that `references/skills/design-system.md` should run next.
   - If present, reference it as the design source and do not duplicate full design tokens in `PAGEWELL.md`.
2. Inspect existing context files.
   - Import useful facts from legacy `SITE_PROFILE.md` into the site implementation sections.
   - Import product facts from `products.*` or equivalent into product facts and claim sections.
   - Preserve legacy files unless the user explicitly asks to remove them.
3. Inspect the repo/framework.
   - Identify framework, rendering mode, route locations, component/layout conventions, metadata conventions, discovery files, commands, and deployment clues.
   - Select a recommended adapter.
4. Inventory product/company facts.
   - Extract only facts supported by repo content or user-provided sources.
   - Mark uncertain facts as unknown instead of inventing.
   - Separate supported claims from prohibited/unknown claims.
5. Inventory page and component patterns.
   - Identify hero patterns, CTA blocks, proof sections, FAQ patterns, comparison tables, docs layouts, tool UI patterns, card grids, related links, and navigation/footer conventions.
   - Prefer source-level observations over visual guesses.
6. Write or update `PAGEWELL.md`.
   - Preserve existing verified facts and user-approved rules.
   - Add new findings with concise source notes when useful.
   - Keep design references pointed to `DESIGN.md`.
7. Call out unknowns.
   - If important claims, pricing, customers, integrations, or product capabilities are uncertain, list them under prohibited/unknown claims and ask for confirmation.

## Required `PAGEWELL.md` structure

Use this structure unless the existing file has a compatible structure:

```md
# PAGEWELL.md

Generated: YYYY-MM-DD
Last reviewed: YYYY-MM-DD

PAGEWELL.md is the Pagewell source of truth for this repo. Use it with `DESIGN.md` before planning, generating, QAing, or maintaining pages.

## Product facts

### Product
- Name:
- URL:
- Category:
- One-sentence description:
- Primary audience:
- Primary CTA:
- Secondary CTA:

### What Pagewell/the product does
- ...

### What Pagewell/the product does not do
- ...

## Supported claims

| Claim | Source | Confidence |
|---|---|---|

## Prohibited or unknown claims

- ...

## Site implementation

### Current repo/site
- Framework:
- Rendering:
- Site root:
- Routes:
- Styling:
- Components:
- Layouts:
- Content:
- Metadata:
- Design source:
- Discovery files:
- Deployment:
- Recommended adapter:

### Commands
- Dev:
- Build:
- Check:
- Preview:

### Implementation conventions
- ...

## Route taxonomy

| Intent | Route pattern | Notes |
|---|---|---|

## Page and component patterns

### Page shell
- ...

### Hero patterns
- ...

### Proof and explanation patterns
- ...

### FAQ and CTA patterns
- ...

### Free-tool UI patterns
- ...

## Generation rules

- Always read `DESIGN.md` and `PAGEWELL.md` before generating or QAing pages.
- Treat playbook section names as required coverage, not literal headings or fixed layout order.
- ...

## Anti-generic QA rules

- ...

## QA rules

- ...
```

## Rules

- Do not modify site behavior while discovering context unless the user explicitly asks.
- Do not delete legacy `SITE_PROFILE.md` or product fact files unless the user asks.
- Do not install packages.
- Do not migrate frameworks.
- Do not invent product claims, metrics, testimonials, customer names, prices, integrations, certifications, or competitor facts.
- If a fact is uncertain, mark it as unknown or prohibited until confirmed.
- Keep `DESIGN.md` separate and do not duplicate its full token set.
- Be specific to the repo; avoid generic context like "uses components" when exact folders/files are known.
- Page patterns should describe reusable site behavior, not prescribe a single page template.

## Acceptance criteria

- `PAGEWELL.md` exists at the repo root.
- It includes product facts, claim rules, site implementation, route taxonomy, page/component patterns, generation rules, anti-generic QA rules, and QA rules.
- It references `DESIGN.md` as the visual source of truth.
- Unsupported or uncertain claims are clearly listed.
- Future Pagewell generation modules can use `PAGEWELL.md` without separately requiring `SITE_PROFILE.md` or a standalone product facts file.

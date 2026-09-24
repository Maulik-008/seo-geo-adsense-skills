# Adapter: Cloudflare Worker

Use this adapter when `PAGEWELL.md` identifies a Cloudflare Worker rendering HTML or routing requests manually.

## Detection

- `wrangler.toml`
- `worker.js` or `src/worker.*`
- `export default { async fetch(request) { ... } }`
- routes configured for a domain

## Recommended implementation strategy

If the Worker is one large inline HTML string, do not keep adding unrelated giant strings. Prefer a small page system first:

```js
const PAGES = [
  {
    path: "/products/requesthunt",
    title: "...",
    description: "...",
    noindex: false,
    sections: [...],
  },
];

function renderPage(page) {}
function renderMeta(page) {}
function renderJsonLd(page) {}
function renderSitemap(pages) {}
function renderRobots() {}
function renderLlmsTxt(pages) {}
```

If a page registry already exists, add to it.

## Routing

- Match exact paths and normalized trailing slashes.
- Redirect `www` to apex if that is the site convention.
- Serve `/robots.txt`, `/sitemap.xml`, and `/llms.txt` explicitly.
- Return a proper 404 page for unknown routes.

## Interactive free tools

For `/tools/*` pages, serve static HTML plus small inline or bundled JavaScript for the tool interaction. Keep the first render crawlable: hero, description, how-to-use, FAQ, and CTA should exist in HTML even if the tool itself uses client-side JavaScript.

## Metadata and schema

Worker-rendered pages must manually include:

- title
- description
- canonical
- robots
- Open Graph/Twitter if used
- JSON-LD script tags

## Rules

- Keep Worker responses fast and static where possible.
- Avoid adding external runtime dependencies.
- Do not duplicate full HTML shells per page if a renderer can be shared.
- For more than a handful of pages, recommend migration to a static framework like Astro, but do not perform migration unless requested.

# Adapter: Next.js

Use this adapter when `PAGEWELL.md` identifies Next.js.

## Detection

- `next.config.*`
- `app/` or `src/app/` for App Router
- `pages/` or `src/pages/` for Pages Router

## App Router implementation

Create route folders with `page.tsx` or `page.jsx`:

```txt
app/products/requesthunt/page.tsx
app/use-cases/find-feature-requests-from-reddit/page.tsx
```

Use existing layouts and metadata conventions. Prefer `export const metadata` or `generateMetadata` if the repo uses them.

## Pages Router implementation

Create files under `pages/` or `src/pages/`:

```txt
pages/products/requesthunt.tsx
pages/use-cases/find-feature-requests-from-reddit.tsx
```

Use existing head/meta component or `next/head`.

## Interactive free tools

For `/tools/*` pages, keep SEO shell/server metadata in the route page and put interactive input/output logic in a client component only when needed. Prefer deterministic client-side processing for v1 free tools.

## Discovery files

Depending on existing convention:

- App Router: `app/robots.ts`, `app/sitemap.ts`, route handlers for `llms.txt`.
- Pages Router: API routes or static files in `public/`.
- Static `public/robots.txt` and `public/llms.txt` are acceptable when sitemap is static or generated elsewhere.

## Rules

- Do not mix App Router and Pages Router conventions unless the repo already does.
- Reuse existing components and styling.
- Avoid adding new dependencies.

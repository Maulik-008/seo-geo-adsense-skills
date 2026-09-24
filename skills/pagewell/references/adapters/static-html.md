# Adapter: Static HTML

Use this adapter when the site is plain HTML files with no framework.

## Implementation

Create route folders with `index.html`:

```txt
products/requesthunt/index.html
use-cases/find-feature-requests-from-reddit/index.html
```

If the site uses includes, partials, or a static generator script, follow that convention.

## Reuse

- Copy the existing header/footer only if no shared include system exists.
- Preserve existing CSS classes and global stylesheet.
- Avoid introducing a new build step unless approved.

## Interactive free tools

For `/tools/*` pages, use plain JavaScript in a colocated script file or inline script following the site's existing pattern. Keep all important explanatory content in the HTML so the page remains useful without executing the tool script.

## Discovery files

Create or update:

```txt
robots.txt
sitemap.xml
llms.txt
```

at the served root, or in `public/` if the repo has a publish folder convention.

## Rules

- Keep pages valid HTML.
- Include canonical, title, meta description, and robots tags manually.
- Exclude private/noindex pages from `sitemap.xml`.

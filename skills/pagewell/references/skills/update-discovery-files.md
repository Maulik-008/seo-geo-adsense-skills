# Skill: Update Discovery Files

## Purpose

Create or update discovery files that help crawlers and AI systems understand the site.

Discovery files include:

- `sitemap.xml`
- `robots.txt`
- `llms.txt`

## Inputs

- `PAGEWELL.md`
- site/page registry or route files
- generated page specs/frontmatter
- existing discovery files

## Rules

### Sitemap

- Include only canonical indexable pages.
- Exclude pages with `noindex`.
- Exclude private/ABM/follow-up pages.
- Use absolute URLs.
- Prefer generated sitemap route if the framework supports it.

### Robots

- Allow normal crawling unless there is a site-specific reason not to.
- Reference sitemap URL.
- Do not block `/llms.txt`.
- Do not rely on robots to protect private information; private pages still need `noindex,nofollow` and should not contain secrets.

### llms.txt

Create or update `/llms.txt` as a factual, compact site summary.

Include:

- Site name and one-sentence description.
- Canonical `PAGEWELL.md` product facts.
- Important indexable pages.
- Durable public free tools that are important to the site.
- Contact/support URL or email if public.

Do not include:

- Hype.
- Unverified claims.
- Private/ABM pages.
- Temporary campaign tools.
- Long marketing copy.

## Implementation rules

- Read the site implementation and recommended adapter from `PAGEWELL.md`.
- For frameworks with route files, implement `robots.txt`, `sitemap.xml`, and `llms.txt` using existing route conventions.
- For static sites, create files in `public/` or output root based on convention.
- For Workers, serve them as explicit routes.

## Acceptance criteria

- `/robots.txt` works.
- `/sitemap.xml` works and excludes noindex pages.
- `/llms.txt` works and is factual.
- Discovery files pass `qa.md` checks.

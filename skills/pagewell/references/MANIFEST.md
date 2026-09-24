# Pagewell Reference Manifest

This directory is packaged with the installable `pagewell` skill.

## Path resolution

When a reference mentions a Pagewell source path, resolve it inside this package:

| Source path | Packaged path |
|---|---|
| `skills/<module>.md` | `references/skills/<module>.md` |
| `playbooks/...` | `references/playbooks/...` |
| `adapters/...` | `references/adapters/...` |
| `docs/...` | `references/docs/...` |
| `schemas/...` | `references/schemas/...` |

## Core modules

- `references/skills/discover-site.md`
- `references/skills/design-system.md`
- `references/skills/define-product-facts.md`
- `references/skills/plan-topic-cluster.md`
- `references/skills/generate-page.md`
- `references/skills/generate-free-tool.md`
- `references/skills/qa.md`
- `references/skills/update-discovery-files.md`
- `references/skills/seo-ops.md`

## Generation routes

| Intent | Read |
|---|---|
| Initialize unified Pagewell context or detect/document a site stack in PAGEWELL.md | `references/skills/discover-site.md` |
| Create, validate, or update design rules | `references/skills/design-system.md` |
| Define product facts and claim sources in PAGEWELL.md | `references/skills/define-product-facts.md` |
| Plan a topic cluster | `references/skills/plan-topic-cluster.md` |
| Generate a standard page | `references/skills/generate-page.md` and the matching `references/playbooks/page-types/*.md` |
| Generate or plan a free tool | `references/skills/generate-free-tool.md` and `references/playbooks/free-tools/*.md` |
| QA a page or claim set | `references/skills/qa.md` and `references/playbooks/qa/claim-check.md` |
| Update discovery files | `references/skills/update-discovery-files.md` |
| Maintain SEO/GEO clusters | `references/skills/seo-ops.md` and `references/playbooks/seo/*.md` |

## Adapters

- `references/adapters/astro.md`
- `references/adapters/nextjs.md`
- `references/adapters/cloudflare-worker.md`
- `references/adapters/static-html.md`
- `references/adapters/unknown-framework.md`

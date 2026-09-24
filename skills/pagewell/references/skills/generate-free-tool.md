# Skill: Generate Free Tool

## Purpose

Plan, generate, hub, or launch no-signup free tools that drive SEO/GEO traffic and route qualified users toward the main product.

Free tools are special because they must provide working utility, not just content.

## Required inputs

- `PAGEWELL.md`
- validated `DESIGN.md`
- tool brief or request
- optional ICP/keyword/community data

## Modes

### Brainstorm

Use when the user asks for tool ideas.

Detailed playbook: `references/playbooks/free-tools/brainstorm.md`

Output:

- ICP summary
- at least 15 tool ideas
- scoring matrix
- recommended top 3
- draft brief for the best first tool

### Generate page

Use when a tool brief exists.

Detailed playbook: `references/playbooks/free-tools/page.md`

Required route pattern:

```txt
/tools/<slug>
```

Required page behavior:

- working input/output interface
- no signup before first value
- result copy/download/share where relevant
- how-to-use section
- example input/output when useful
- product CTA
- related tools/internal links
- FAQ
- `WebApplication` schema for indexable tools

### Generate/update tools hub

Use when creating or maintaining `/tools`.

Detailed playbook: `references/playbooks/free-tools/hub.md`

The hub should list only public/indexable tools and link them by category/use case.

### Launch

Use after a tool is deployed or ready to deploy.

Detailed playbook: `references/playbooks/free-tools/launch.md`

Output:

- Day 1 launch checklist
- social/community post drafts
- demo video script
- internal-link tasks
- analytics verification
- Week 1 follow-up tasks

## Framework-neutral implementation rules

- Read `PAGEWELL.md`, including product facts, claim rules, site implementation, route taxonomy, page/component patterns, generation rules, and anti-generic QA rules.
- Read `DESIGN.md` and follow its tokens/prose.
- Treat required page sections as coverage requirements, not literal headings or fixed order.
- Do not assume React/Next.js.
- Prefer deterministic client-side logic for v1.
- If backend/API processing is required, explain why and follow existing backend conventions.
- Keep the SEO shell crawlable: hero, description, how-to-use, FAQ, and CTA should exist in HTML.
- Do not add dependencies without approval when a small script will work.

## Lead capture rules

Lead capture must not block first value.

Allowed:

- CTA after result generation.
- Email capture after repeated uses or time delay.
- Product CTA section.
- Powered-by link.

Not allowed:

- Signup wall before first result.
- Fake tool that only captures email.
- Dark patterns that obscure the free utility.

## Acceptance criteria

- Tool provides useful output without authentication.
- Tool page follows `DESIGN.md`, `PAGEWELL.md`, and current framework conventions.
- Metadata and schema are correct.
- Discovery files are updated when indexable.
- Launch plan exists when requested.
- Page passes `references/skills/qa.md`.

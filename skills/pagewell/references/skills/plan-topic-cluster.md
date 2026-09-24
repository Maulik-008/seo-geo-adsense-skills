# Skill: Plan Topic Cluster

## Purpose

Plan a topical authority cluster for a product, ICP, or seed keyword.

This is an orchestration/planning skill. It does **not** directly generate pages. It outputs page briefs and an internal-link map, then tells the agent which Pagewell skills to run next.

Detailed strategy: `references/playbooks/seo/maintenance.md`, `references/docs/topical-authority-strategy.md`, and `references/docs/faq-glossary-strategy.md`.

## Required inputs

- `PAGEWELL.md`
- `DESIGN.md`
- seed topic or product
- ICP
- optional keyword/search data
- optional existing URL inventory

## Candidate page types

Plan across these types when they fit the topic:

- product/entity pages
- use-case/workflow pages
- FAQ/question pages
- glossary/definition pages
- free tools/utilities
- docs/tutorials
- alternative/comparison pages

## Process

1. Identify the core product/topic.
2. Define ICP and jobs-to-be-done.
3. Inventory existing pages if possible.
4. Generate candidate pages by intent type.
5. Score each candidate:
   - search intent
   - conversion fit
   - product fit
   - build effort
   - uniqueness/opportunity
   - internal-link value
6. Select a practical first cluster.
7. Output page briefs.
8. Output internal-link map.
9. Recommend execution order.

## Output format

Return a markdown plan with this shape:

````md
# Topic Cluster Plan: <Topic>

## ICP
...

## Existing coverage
- ...

## Recommended cluster

| Priority | Page Type | Route | Primary Intent | Next Skill |
|---:|---|---|---|---|

## Page briefs

### <route>
```yaml
route: ...
pageType: ...
...
```

## Internal-link map

- Hub page → supporting pages
- Supporting pages → hub page
- Related FAQ/glossary/tool links

## Execution order

1. ...
````

## Recommended minimum cluster

A balanced first cluster usually includes:

- 1 product or hub page
- 2-4 use-case pages
- 3-8 FAQ pages
- 3-8 glossary pages
- 1-3 free tools when useful
- 1-2 alternatives/comparisons when factual

## Rules

- Do not generate pages directly from this skill.
- Do not recommend pages without a real search, conversion, support, or outbound intent.
- Avoid near-duplicate FAQ or glossary pages.
- Prefer fewer high-signal pages over mass low-value generation.
- For alternatives/comparisons, require `references/skills/qa.md` claim checks.

## Acceptance criteria

- Plan includes page briefs, not just ideas.
- Every page maps to a specific intent.
- Execution order is clear.
- Internal-link map connects the cluster.

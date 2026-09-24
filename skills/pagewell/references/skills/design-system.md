# Skill: Design System

## Purpose

Create, update, or validate `DESIGN.md`, the website's durable visual identity contract for agents.

Pagewell strictly uses the Google Labs Code `DESIGN.md` specification. Do not invent a Pagewell-specific design format.

- Canonical spec repo: https://github.com/google-labs-code/design.md
- CLI/package: `@google/design.md`
- Spec command: `bunx @google/design.md spec --rules`
- Lint command: `bunx @google/design.md lint DESIGN.md`

## When to use

- `DESIGN.md` does not exist.
- The site design changed.
- Page-generation skills need a validated design source of truth.
- The user asks to extract, update, or validate site design.

## Inputs

- `PAGEWELL.md` or legacy `SITE_PROFILE.md` if present.
- Existing homepage, layouts, components, global CSS, Tailwind config, or inline styles.
- Existing logo/icon SVGs and product cards.
- Optional screenshots or visual references supplied by the user.
- Existing `DESIGN.md` if present.

## Modes

### Extract

Create `DESIGN.md` from the current site.

1. Read `PAGEWELL.md` if available, or legacy `SITE_PROFILE.md` if present.
2. If possible, inspect the current spec:

   ```bash
   bunx @google/design.md spec --rules
   ```

3. Identify the canonical visual surface, usually the homepage or main marketing layout.
4. Extract exact values where possible:
   - colors
   - typography
   - spacing scale
   - rounded corners/shapes
   - layout widths and rhythm
   - elevation/depth rules
   - button, card, command/code block, input, and navigation styles
5. Write `DESIGN.md` using Google `DESIGN.md` YAML tokens and canonical section order.
6. Prefer token references in `components` so tokens are reusable.

### Validate

Validate an existing `DESIGN.md`.

1. Confirm the file exists at repo root.
2. Run when possible:

   ```bash
   bunx @google/design.md lint DESIGN.md
   ```

3. Fix all linter errors.
4. Address warnings when practical, especially:
   - missing `primary` color
   - missing typography
   - broken references
   - low contrast
   - out-of-order sections

### Update

Update `DESIGN.md` after design changes.

1. Preserve the Google spec format.
2. Preserve existing useful prose.
3. Update tokens to reflect the current canonical design.
4. Re-run validation.

## Required token schema

Use only the schema accepted by the Google spec in YAML front matter:

```yaml
version: <string>
name: <string>
description: <string>
colors:
  <token-name>: <Color>
typography:
  <token-name>: <Typography>
rounded:
  <scale-level>: <Dimension>
spacing:
  <scale-level>: <Dimension | number>
components:
  <component-name>:
    <token-name>: <string | token reference>
```

## Canonical section order

Sections can be omitted, but included `##` sections must appear in this order:

1. `Overview` or `Brand & Style`
2. `Colors`
3. `Typography`
4. `Layout` or `Layout & Spacing`
5. `Elevation & Depth` or `Elevation`
6. `Shapes`
7. `Components`
8. `Do's and Don'ts`

## Rules

- Strictly use the Google Labs Code `DESIGN.md` spec.
- Prefer exact values from source code over guesses.
- Preserve existing brand personality.
- Keep prose actionable for page-generation agents.
- Do not refactor the site while extracting design.
- Do not proceed with a `DESIGN.md` that has linter errors unless the user explicitly accepts the failure.

## Acceptance criteria

- `DESIGN.md` exists at repo root.
- It has zero linter errors with `bunx @google/design.md lint DESIGN.md` when validation is possible.
- It includes machine-readable tokens and human-readable rationale.
- It includes component guidance for important site patterns.
- It says what not to do visually.

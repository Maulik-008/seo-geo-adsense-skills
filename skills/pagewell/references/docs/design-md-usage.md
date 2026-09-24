# DESIGN.md Usage

Pagewell strictly uses the Google Labs Code `DESIGN.md` specification.

- Canonical spec repo: https://github.com/google-labs-code/design.md
- CLI/package: `@google/design.md`
- Spec command: `bunx @google/design.md spec --rules`
- Lint command: `bunx @google/design.md lint DESIGN.md`

Do not invent or use a Pagewell-specific design file format.

## Required behavior

Every Pagewell page-generation skill must:

1. Read `DESIGN.md` before generating UI.
2. Treat YAML front matter tokens as normative values.
3. Treat Markdown prose as application guidance.
4. Preserve the existing visual identity.
5. Avoid colors, typography, spacing, and component styles not supported by `DESIGN.md` or existing site code.

## Google DESIGN.md structure

A valid `DESIGN.md` contains:

1. Optional YAML front matter with design tokens.
2. Markdown body sections with design rationale.

Supported token groups:

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

Sections can be omitted, but included `##` sections should appear in this order:

1. `Overview` / `Brand & Style`
2. `Colors`
3. `Typography`
4. `Layout` / `Layout & Spacing`
5. `Elevation & Depth` / `Elevation`
6. `Shapes`
7. `Components`
8. `Do's and Don'ts`

## Validation

Run:

```bash
bunx @google/design.md lint DESIGN.md
```

A generated `DESIGN.md` must have zero linter errors. Warnings should be fixed when practical or documented when acceptable.

## Exporting tokens

When useful, export tokens with the official CLI:

```bash
bunx @google/design.md export --format tailwind DESIGN.md > tailwind.theme.json
bunx @google/design.md export --format dtcg DESIGN.md > tokens.json
```

Do not rely on exported files as the source of truth. `DESIGN.md` remains canonical.

# Adapter: Unknown or Custom Framework

Use this adapter when the site does not clearly match a known framework.

## Process

1. Inspect existing routes and find the closest page similar to the requested one.
2. Identify how it handles:
   - route path
   - layout/shell
   - metadata
   - content source
   - styling
   - build/deploy
3. Mirror that pattern exactly.
4. If the implementation path is unclear, stop and propose a minimal plan instead of guessing.

## Safe defaults

- Do not add dependencies.
- Do not invent a new routing system.
- Do not migrate frameworks.
- Prefer adding data/content to an existing registry over creating a parallel system.

## Acceptance criteria

- New page follows existing conventions.
- The user can review a small, understandable diff.

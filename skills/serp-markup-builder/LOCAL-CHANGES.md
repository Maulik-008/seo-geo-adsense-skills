# Local changes

**Upstream:** [aaron-he-zhu/aaron-marketing-skills](https://github.com/aaron-he-zhu/aaron-marketing-skills) — `seo-geo/implement/serp-markup-builder`, version 20.1.0, commit `5a1b2360eb9b61e8fb94e9403ff5f399ff40f765` (2026-09-24).
**License:** Apache-2.0 (see `LICENSE`). This file is the notice of modifications required by §4(b).
**Imported:** 2026-09-24, into the `SEO_ADSENSE_GEO` skill set.

## What changed

- Relative links were rewritten so the skill works as a standalone folder:
  - links to bundled files → local paths;
  - `content-writer` → `human-web-content`; `technical-seo-checker` / `on-page-seo-checker` → `seo-geo`;
  - links to skills and files that are not installed → GitHub, pinned to the commit above.
- Bundled `scripts/schema_lint.py` and its helpers `_loader.py`, `_http.py`, `robots.py` (unmodified), plus shared references in `references/shared/`.
- `SKILL.md`: added **Local install rules** (no invisible or fake review/rating/author/date values, missing connectors); pointed the `schema_lint` commands at the bundled script.
- Added `references/human-title-rules.md` (local, not upstream): human-sounding title and description rules that override the upstream title formulas.

## Updating

Re-clone upstream, re-run the import (copy the skill tree plus the files listed above), re-apply the `SKILL.md` edits, and bump the commit here. Do not hand-edit files under `references/shared/` or `scripts/`; they must stay identical to upstream.

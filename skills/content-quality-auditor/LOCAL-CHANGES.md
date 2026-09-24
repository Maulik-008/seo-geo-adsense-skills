# Local changes

**Upstream:** [aaron-he-zhu/aaron-marketing-skills](https://github.com/aaron-he-zhu/aaron-marketing-skills) — `seo-geo/tune/content-quality-auditor`, version 20.1.0, commit `5a1b2360eb9b61e8fb94e9403ff5f399ff40f765` (2026-09-24).
**License:** Apache-2.0 (see `LICENSE`). This file is the notice of modifications required by §4(b).
**Imported:** 2026-09-24, into the `SEO_ADSENSE_GEO` skill set.

## What changed

- Relative links were rewritten so the skill works as a standalone folder:
  - links to bundled files → local paths;
  - `content-writer` → `human-web-content`; `technical-seo-checker` / `on-page-seo-checker` → `seo-geo`;
  - links to skills and files that are not installed → GitHub, pinned to the commit above.
- Bundled the root runtime inside this skill: `references/shared/` (runbook, scoring semantics, benchmark, run schema, runtime-invocation, skill contract, humanizer check, SECURITY), `references/framework-catalog.json`, and `scripts/rubric-score.py`. All are unmodified upstream files, so the bundled scorer produces real `SCORED` results instead of the upstream standalone `NOT_SCORED` fallback.
- `SKILL.md`: added **Local install**; rewrote Runtime Reads and Runtime Contract to use the bundled paths; added routing to local skills; marked **Persistence** unavailable (the artifact validator is not bundled).
- Added `references/local-overrides.md`: evidence and fix-recommendation rules that keep scoring consistent with `human-web-content`, `clarity`, and `adsense-auditor`. It does not change IDs, weights, vetoes, or the scorer.

## Updating

Re-clone upstream, re-run the import (copy the skill tree plus the files listed above), re-apply the `SKILL.md` edits, and bump the commit here. Do not hand-edit files under `references/shared/` or `scripts/`; they must stay identical to upstream.
